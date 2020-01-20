Retrieve your weather station's data from La Crosse Technology's cloud storage

Example:

.. code-block:: python

    # Get the latest temperature value from a device named 'temperature'
    # First setup your La Crosse View app
    email = 'ENTER YOUR LA CROSSE E-MAIL HERE'
    password = 'ENTER YOUR LA CROSSE PASSWORD HERE'
    print("Logging in...")
    token = lacrosse_login(email, password)
    print("Getting locations...")
    locations = lacrosse_get_locations(token)
    print("Getting devices...")
    devices = lacrosse_get_devices(token, locations)

    for device in devices:
        if device['device_name'] == 'temperature':
            weather_data = lacrosse_get_weather_data(token, device)
            print("Current temperature is: {} {}".format(weather_data['Temperature']['values'][-1]['s'], weather_data['Temperature']['unit']))

Credit for original code: https://github.com/dbconfession78/py_weather_station
