## Locator ##
### Overview ###
Add a geographic search box to an application. The widget defaults to the ArcGIS Online World Geocoding Service but can be customized to use one or more ArcGIS Server geocoding services.

### Attributes ###
* `arcgisGeocoder` boolean; optional; default: true; By default, the Locator widget uses the Esri World Locator to find search locations. Disable this locator by setting this property to false. The Esri World Locator can be configured by specifying an object with the following properties:

>> 
- url: Url of the geocoder. When undefined the ArcGIS World Geocoder is used.
- name: Name of the geocoder. If you've specified multiple geocoders this is the name that will appear in the dropdown list.
- placeholder: Placeholder text that will appear in the input box.
- outFields: An optional list of out fields.
- prefix: Text that will be prepended to the search string. Note that since the text is appended you may need to add a space to the end of your prefix string. For example prefix:" coffee"
- suffix: Text that will be appended to the search string. Note that since the text is appended you may need to add a space to the beginning of your suffix string. For example suffix:" Charlotte, NC"
- searchExtent: Restrict the search to the specified extent.
- sourceCountry: Country code to use for the search. Using a country code can improve location search performance. Specify the sourceCountry using a valid country code from this list.
- localSearchOptions:
- minScale: Location search will be performed when the map scale is less than the specified value. The default minScale is 15,000.
- distance: Specify a search distance for the location search. The default value is 12,000 meters.
Example:
```
"arcgisGeocoder": {
  	    "placeholder": "World address or places"
  	}
```

* `geocoders` []; optional; Defines the geocoders that will be used by the Geocoder widget. If arcgisGeocoder is true then the geocoders will be used alongside the default arcgisGeocoder. When false, the default arcgisGeocoder will not be used. Geocoders is an array of objects that define the additional geocoders. Each object includes the name, url to the locator service and the name of the field setup to accept single line input. i.e. 'SingleLineFieldName' or 'SingleLine'. 

Example:
```
"geocoders": [{
  		"url" : "http://ismaelgis:6080/arcgis/rest/services/LeasesWells/GeocodeServer",
  		"name": "Leases / Wells Geocoder",
    	"singleLineFieldName": "SingleKey",
    	"placeholder": "Find Leases / Wells"
  	}]
```
