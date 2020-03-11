<b>This app is based on the Flask framework and ArcGis (```https://developers.arcgis.com/sign-up/```) to geocode locations basing on provided data.</b>

<i>Before you moved: as this is the flask app, make sure you installed all required modules described in ```requrements``` file (e.g. ```pip3 install Flask```)</i><br>

<u>How to run the the app<u>
1. Clone/Download current repository and open the folder and open in your IDE (PyCharm, Sublime, etc.)
2. The app allows user to upload csv file which consist of headings: point(name of the place), latitude, longitude. You may find an example of such CSV file in the static folder ("data_sample.csv") and use it. Please note, that csv data should consist delimiter "," . Don't forget to include all required data into the csv file.
2. In order to run the app, please open IDE terminal. Make sure you are in the root folder. You can navigate inside between the folders using ```cd/ls``` comands.
3. Once you are ready to run an application, please type "flask run" in your oppened terminal. You should see the message 
  ```" * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)"```.
4. Open your bash terminal in a separate window. You can use cUrl command-line tool to upload the csv file and get proper results.
  4.1. Type ```curl http://127.0.0.1:5000/getAddresses -d 'file=http://127.0.0.1:5000/static/data_sample.csv'``` , where:
        ```http://127.0.0.1:5000/getAddresses``` - app url
        ```-d``` - Sends the specified data in a POST request to the HTTP server, in the same way that a browser does when a                      user has filled in an HTML form and presses the submit button.
        ```http://127.0.0.1:5000/static/data_sample.csv``` - file destination
 5. The app should return the json result which consist of:
    - ```links```, which include all posible direct names between the locations and destinations between them, and
    - ```points```, which stores detailed information regarding the locations you provided in your csv file. This infromation was collected from the ArcGis API using the special arcgis function (```reverse_geocode```, for more details ```https://developers.arcgis.com/python/guide/reverse-geocoding/```)
