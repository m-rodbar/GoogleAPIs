%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%                                                                                     %
%  Workspace: MRB                                                                     %
%  Author:    Manuel Rodriguez-Barrientos Diaz                                        %
%  Date:      01-10-2017                                                              %
%                                                                                     %
%  Used Resources:	ReadyAPI 2.1.0                                                    %
% 					Microsoft Excel                                                   %
%					Notepad++                                                         %
%                                                                                     %
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%


%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
Project: 		Geolocation
SoapUI file: 	Geolocation-readyapi-project
Test Object: 	Google Maps Geolocation API
URL: 			https://www.googleapis.com/geolocation/v1/geolocate?key=YOUR_API_KEY
%%%%%%%%%


%% Preconditions: %%
1. Insert a valid Google API key in the Project custom property "GoogleKey".

%% Instructions: %%

1. Syntax Validation Test Suite. Validates the syntax of requests and returned response.

2. Error Cases Test Suite. Validates the different error responses received.

	2.a Daily Limit Rate. This test step requires setting the maximum user allowed rate 
	of usage to a small value that can be easily exceeded.

	2.b Rate Limit. This test step requires lowing the maximun user allowed daily rate 
	of usage to a value that can be exceeded.

3. Location Test Suite.

	3.a A list of cellTowers was taken from the internet. This has been used as input data, 
	using the "cellTowers data.xls" file.

	3.b Test Suit properties are taken from file "WiFi Access Points - Properties". This 
	provides the WiFi APs used in the tests. Content of the file might to be updated since 
	mac addresses may change in time.
	TODO. Handle cellTowers details as properties for the sake of usability.

4. "Result Validation" Test Suite.
	4.a The "get Results" Test Case can be used to obtain the location of cells. Obtain 
	locations are stored in the "cellTowers data.xls" file for later reference.
	The test case is disabled since it is not intended to be executed as part of the
	regression.

	4.b The "validate Results" Test Case can be used to regression the service in order 
	to ensure that some location is returned after any service update. Values obtained by 
	the "get Results" Test Case in the "cellTowers data.xls" file are used as input and 
	asssertion data.


%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
Project: 		Timezone
SoapUI file: 	Timezone-readyapi-project
Test Object: 	Google Maps Timezone API
URL: 			https://maps.googleapis.com/maps/api/timezone/json?
%%%%%%%%%

%% Preconditions: %%
1. Insert a valid Google API key in the Project custom property "GoogleKey".

%% Instructions: %%

1. Syntax Validation Test Suite. Validates the syntax of requests and returned response.

2. Error Cases Test Suite. Validates the different error responses received.

	2.a Overquery Limit Rate. This test step requires setting the maximum user allowed rate 
	of usage to a small value that can be easily exceeded.

	2.b Unkwown Error. This test step requires obtaining an unknown error response from the 
	service.

3. Timezone Test Suite.

	3.a A list of capitals of the world and their latitude and longitude was taken from 
	the internet. This has been used as input data, using the "World Around.xls" file.

	3.b The "DST offset" Test Case validates the DST change in the city of Madrid.

4. "Result Validation" Test Suite.

	4.a The "get Results YearRound" Test Case can be used to obtain the timezone values for
	the city of Madrid for the first day of each month in the year 2017. Obtained values are
	stored in the "Madrid.xls" file for later reference.
	The test case is disabled since it is not intended to be executed as part of the regression.
	
	4.b The "get Results WorldAround" Test Case can be used to obtain the timezone values for
	the world capitals on January, 1st 2017. Obtained values are stored in the "World Around.xls" 
	file for later reference.
	The test case is disabled since it is not intended to be executed as part of the regression.
	
	4.c The "validate Results YearRound" Test Case can be used to regression the service in order 
	to ensure that some timezones are returned after any service update. Values obtained by the
	"get Results YearRound" Test Case in the "Madrid.xls" file are used as input and asssertion
	data.

	4.d The "validate Results WorldAround" Test Case can be used to regression the service in order 
	to ensure that some timezones are returned after any service update. Values obtained by the
	"get Results WorldAround" Test Case in the "World Around.xls" file are used as input and 
	asssertion data.
	
