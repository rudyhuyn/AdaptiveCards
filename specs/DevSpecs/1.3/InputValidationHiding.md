# InputValidation

## Proposal Link
https://github.com/microsoft/AdaptiveCards/issues/3081

## Dependencies
None

## Backwards Compatibility Concerns
None

## Warning and Error States
 - If a cards author sets an error message without marking it as "isRequired", or without setting a regex, a warning should be returned
 - If a regex is provided that is not a regular expression an error should be returned (?)

 ## Open Issues
 TODO

 ## Testing

### Object Model
All Object model test suites should be updated to validate the new properties. Specifically:
- inputNecessityIndicators property on the top level card.
- IsRequired and ErrorMessage properties on inputs
- Regex on Input.Text
- IgnoreInputValidation on Action.Submit

 Test suites that should be updated:
- Shared model, via the EverythingBagel tests.
- UWP Object Model unit tests
- Android object model tests.

Additionally, error and warning cases should be tested. For shared model platforms this testing will take place in the shared model unit tests.

### Samples
The following samples will be added to validate rendering of input validation:
- Action.Submit.IgnoreInputValidation.json file which contains required inputs and a submit action which ignores validation
- AdaptiveCard.InputNecessityIndicators.json file which sets this property on the top level card
- Input.Text.IsRequired.json file which has required and optional inputs
- Input.Text.Regex.json file which has both required and optional text inputs with regexs