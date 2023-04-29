# geocoded
Geocoding Using Geopy & Python

Geocoding is the process of converting a human-readable address or location description (such as a street address, city name, or landmark) into geographic coordinates (such as latitude and longitude). This allows the address or location to be accurately plotted on a map or used in a geographic information system (GIS).

Geocoding is typically performed by software programs called geocoders, which use a combination of reference data, algorithms, and heuristics to match the input address or location description to a specific geographic location. The reference data used by geocoders can include street maps, address databases, and satellite imagery, among others.

Geocoding is used in a variety of applications, such as mapping and navigation software, emergency services, and location-based advertising. It is also an important tool for urban planners, environmental scientists, and other professionals who need to analyze and visualize spatial data.

This code is written in Python and uses the Pandas and Geopy libraries to read an input CSV file containing addresses, geocode the addresses to obtain latitude and longitude coordinates, and then save the results to a new output CSV file.

Here is a step-by-step breakdown of the code:

The first line imports the Pandas library, which provides data structures and tools for data analysis.

The second line imports the Nominatim geocoder class from the Geopy library, which provides a way to geocode addresses and obtain their latitude and longitude coordinates.

The third line reads the input CSV file into a Pandas DataFrame using the read_csv() method. The path to the input CSV file is specified using the r prefix to indicate that it is a raw string and the backslashes should be interpreted literally.

The fourth line initializes a Nominatim geocoder object with a user agent string and a timeout of 10 seconds. The user agent string is a unique identifier that allows the geocoder service to track usage and prevent abuse.

The fifth line defines a new function called get_location() that takes an address as input and returns a tuple of the latitude and longitude coordinates. The function uses the geocode() method of the geocoder to obtain the location object for the address. If the location object is None, indicating that the address could not be geocoded, the function returns None for both latitude and longitude. Otherwise, it returns the latitude and longitude values of the location object.

The sixth line uses the apply() method of the DataFrame to apply the get_location() function to the 'address' column of the DataFrame. The zip() function is used to unpack the tuple of latitude and longitude values returned by get_location() into separate 'latitude' and 'longitude' columns in the DataFrame.

The seventh line saves the output DataFrame to a new CSV file using the to_csv() method of Pandas. The path to the output CSV file is specified using the r prefix to indicate that it is a raw string and the backslashes should be interpreted literally. The index parameter is set to False to exclude the index column from the output CSV file.
