# CityNameAutocomplete

Assists input of city name in registration or checkout form. When user enters a few characters it shows a dropdown with city variants.
It's possible to select a variant by either clicking on it or by navigations with keyboard arrows and pressing enter. When selected a variant will be copied to the input field of city name.

## Installation

In order to pull the latest version:

### npm (preferred)

```
npm i @endereco/citynameautocomplete
```

### github

```
git clone https://github.com/Endereco/CityNameAutocomplete.git
```

Then include CityNameAutocomplete.js in `<header>` or before config.

## Configuration

In order to use city name autocomplete you must specify the fields that make the postcode, city name and country, and some colors.

Here is an example configuration:

```
new CityNameAutocomplete({
    'inputSelector': 'input[name="register[billing][city]"]',
    'secondaryInputSelectors': {
        'postCode': 'input[name="register[billing][zipcode]"]',
        'country': 'select[name="register[billing][country]"]'
    },
    'endpoint': 'https://example-domain.com/endpoint',
    'apiKey': '041c3c302746cf37722560a7a285690738a7db4e55b7aaf26a545ffabd318a83',
    'colors' : {
       'primaryColor' => '#fff',
       'primaryColorHover' => '#fff',
       'primaryColorText' => '#fff',
       'secondaryColor' => '#fff',
       'secondaryColorHover' => '#fff',
       'secondaryColorText' => '#fff',
       'warningColor' => '#fff',
       'warningColorHover' => '#fff',
       'warningColorText' => '#fff',
       'successColor' => '#fff',
       'successColorHover' => '#fff',
       'successColorText' => '#fff'
   }
});
```

## Dependencies

CityNameAutocomplete relies on StatusIndicator to mark fields green on correct input.

CityNameAutocomplete also relies on Accounting to generate the tid and track transactions.

## Methods

### updateConfig(object newConfig)

Updates inner config. Existing fields are overwritten, new fields are added, other field are kept.

### checkIfFieldsAreSet()

Checks if all relevant fields are set and marks the service as "dirty", if there was a change. Dirty state trigger reinitialisation.

### getPredictions()

Get a list of possible city names and eventually postcodes for the provided input. Returns a promise that is resolved once the answer from remote server is in.


### renderDropdown()

Renders the autocomplete list.

### removeDropdown()

Removes autocomplete list from DOM.
