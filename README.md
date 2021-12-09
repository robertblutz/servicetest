# Service Test example

Since creating the actual tests for the specified service will take some time, I am going to start by providing a general overview of my approach to this coding problem here, and will add the actual test code as I go along.  

Tests for GET functions:
- Run GET with no SKU ID, ensure the output can be deseralized;
- Run GET with a valid SKU ID, ensure that correct result is returned
- Run GET with an invalid ID, verify that no data is returned

Tests for POST functions:
- POST with a new, description and price, verify output; Follow up and verify that a GET function can be run on the newly created SKU
- POST to update an existing SKU (change price and description) and verify changes with a GET
- POST with malformed data (verify error)

Test for DELETE operation:
- DELETE with a valid SKU ID; verify with a GET that no data is returned for that SKU afterward
- DELETE with an invalid SKU ID, verify result (TBD)

Issues with testing this service:
- Based on what I have been able to determine so far, SKU names seem to be arbitrary, and the user can quite easily create a SKU with a string that cannot be retrieved with a simple GET command.  I see some previous users of this service have used GUIDs for their SKU IDs, which although it makes retrieving the SKUs easier, it's not exactly readable for humans.
- Attempting to use the service with Postman results in authentication token errors.  This might just be my lack of knowledge, but it would be useful to have instructions on where to get an auth token for this.
