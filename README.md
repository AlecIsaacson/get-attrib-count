# get-attrib-count
This app uses New Relic's GraphQL API to generate a list of all event types found in your New Relic account.  For each event type found, it then queries for number of attributes associated with the event type.

It's the equivalent to doing this in NRQL:

  `show event types`

Then for each event type:

  `FROM (eventType) SELECT keyset()`
  
The output is formatted *eventType, numberOfAttributes* with one event type per line
  
We output to the console, so you'll need to redirect to a file if you want to view this info in an editor or spreadsheet.

The utility takes the following command line arguments:

`-apikey : [REQUIRED] A user API key that is good for the account you want to pull data from.`  
`-accountId : [REQUIRED] The ID of the account you want to pull data from.`  
`-verbose : Increases the verbosity of the app's output for troubleshooting purposes.  This is an optional switch.`

As an example, this will pull the number attributes for every event type in an account:

`./get-attrib-count -apikey *yourAPIKey* -accountId *yourAccountID`
