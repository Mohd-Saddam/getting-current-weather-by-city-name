# getting-current-weather-by-city-name


'''
Weather forecast with Python
By:Saddam
'''

#import the necessary package!
import requests
try:
    #input the city name
    city = input('Enter the city name:')
    print(city)

    # or you can also hard-code the value
    # city = 'New Delhi'

    #Display the message!
    print('Displaying Weater report for: ' + city)

    #fetch the weater details
    url = 'https://wttr.in/{}'.format(city)
    res = requests.get(url)
    print(res.status_code)
    if res.status_code == 200:
        print(res)

        #display the result!
        print(res.text)
    else:
        print("Failed to retrieve weather data.")
except Exception as e:
    print("Something went worng.")
Enter the city name:Meerut
Meerut
<img width="1318" alt="Screenshot 2023-06-13 at 3 55 30 PM" src="https://github.com/Mohd-Saddam/getting-current-weather-by-city-name/assets/50014573/189a5f30-88ce-4cc5-ac43-5316f3f3320d">



 
