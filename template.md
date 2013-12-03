## Locator ##
### Overview ###
Add a geographic search box to an application. The widget defaults to the ArcGIS Online World Geocoding Service but can be customized to use one or more ArcGIS Server geocoding services.

### Attributes ###
* `arcgisGeocoder`: boolean || object; optional; default: `true`; By default, the Locator widget uses the Esri World Locator to find search locations. Disable this locator by setting this property to false. The Esri World Locator can be configured by specifying an object with the following properties:

  * `url`: string; optional; default: ;Url of the geocoder. When undefined the ArcGIS World Geocoder is used.
  * `name`: string; optional; default: ; Name of the geocoder. If you've specified multiple geocoders this is the name that will appear in the dropdown list.
  * `placeholder`: string; optional; default: ; Placeholder text that will appear in the input box.
  * `outFields`: string; optional; default: ;An optional list of out fields.
  * `prefix`: string; optional; default: ;Text that will be prepended to the search string. Note that since the text is appended you may need to add a space to the end of your prefix string. For example prefix:" coffee"
  * `suffix`: string; optional; default: ;Text that will be appended to the search string. Note that since the text is appended you may need to add a space to the beginning of your suffix string. For example suffix:```" Charlotte, NC"```
  * `searchExtent`: object; optional; default: ;Restrict the search to the specified extent.
  * `sourceCountry`: string; optional; default: ;Country code to use for the search. Using a country code can improve location search performance. Specify the sourceCountry using a valid country code from this list.
  * `localSearchOptions`:
  * `minScale`: number; optional; default: ;Location search will be performed when the map scale is less than the specified value. The default minScale is 15,000.
  * `distance`: number; optional; default: ;Specify a search distance for the location search. The default value is 12,000 meters.

Example 1:
```
"arcgisGeocoder": {
  	    "placeholder": "World address or places"
  	}
```

* `autoComplete`: boolean; optional; default: `false`; When false, the geocoder will not display the auto-complete results menu. The default value is false.
* `autoNavigate`: boolean; optional; default: `true`; When false, the geolocator will not navigate to the result after selection or search.
* `geocoderMenu`: boolean; optional; default: `false`; When false, the geocoder menu will not be displayed when more than one geocoder is set.
* 
* `geocoders`: []; optional; Defines the geocoders that will be used by the Geocoder widget. If `arcgisGeocoder` is true then the `geocoders` will be used alongside the default arcgisGeocoder. When `false`, the default arcgisGeocoder will not be used. Geocoders is an array of objects that define the additional geocoders. Each object includes the name, url to the locator service and the name of the field setup to accept single line input. i.e. 'SingleLineFieldName' or 'SingleLine'. 

Example:
```
"geocoders": [{
  		"url" : "http://ismaelgis:6080/arcgis/rest/services/LeasesWells/GeocodeServer",
  		"name": "Leases / Wells Geocoder",
    	"singleLineFieldName": "SingleKey",
    	"placeholder": "Find Leases / Wells"
  	}]
```

* `maxLocations`: number; optional; default: 6; Maximum number of results to return.
* `minCharacters`: number; optional; default: 3; Minimum number of characters entered into the search field before querying for results.
* `searchDelay`: number; optional; default: 350; Number of milliseconds before querying for results will begin.
* `showResults`: boolean; default: `true`; When false, the geocoder will not show search suggestions while typing.
* `theme`: string; optional; default: "simpleGeocoder"; Specify a theme for the geocoder. The widget has two out-of-the-box themes: simpleGeocoder and arcgisGeocoder. Create a custom theme by adding css classes for your them.
* `value`: string; optional; default:;Start the geocoder with a default value.

