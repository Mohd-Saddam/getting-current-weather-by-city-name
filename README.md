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
Displaying Weater report for: Meerut
200
<Response [200]>
Weather report: Meerut

      \   /     Sunny
       .-.      +48(53) °C     
    ― (   ) ―   → 30 km/h      
       `-’      10 km          
      /   \     0.0 mm         
                                                       ┌─────────────┐                                                       
┌──────────────────────────────┬───────────────────────┤  Tue 13 Jun ├───────────────────────┬──────────────────────────────┐
│            Morning           │             Noon      └──────┬──────┘     Evening           │             Night            │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│     \   /     Sunny          │     \   /     Sunny          │     \   /     Sunny          │     \   /     Clear          │
│      .-.      +40(41) °C     │      .-.      +47(52) °C     │      .-.      +43(45) °C     │      .-.      40 °C          │
│   ― (   ) ―   → 30-35 km/h   │   ― (   ) ―   → 30-35 km/h   │   ― (   ) ―   → 35-40 km/h   │   ― (   ) ―   → 25-36 km/h   │
│      `-’      10 km          │      `-’      10 km          │      `-’      10 km          │      `-’      10 km          │
│     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
                                                       ┌─────────────┐                                                       
┌──────────────────────────────┬───────────────────────┤  Wed 14 Jun ├───────────────────────┬──────────────────────────────┐
│            Morning           │             Noon      └──────┬──────┘     Evening           │             Night            │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│     \   /     Sunny          │     \   /     Sunny          │     \   /     Sunny          │     \   /     Clear          │
│      .-.      40 °C          │      .-.      +47(51) °C     │      .-.      42 °C          │      .-.      +35(36) °C     │
│   ― (   ) ―   → 25-28 km/h   │   ― (   ) ―   → 30-34 km/h   │   ― (   ) ―   ↘ 21-24 km/h   │   ― (   ) ―   ↓ 27-33 km/h   │
│      `-’      10 km          │      `-’      10 km          │      `-’      10 km          │      `-’      10 km          │
│     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
                                                       ┌─────────────┐                                                       
┌──────────────────────────────┬───────────────────────┤  Thu 15 Jun ├───────────────────────┬──────────────────────────────┐
│            Morning           │             Noon      └──────┬──────┘     Evening           │             Night            │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│     \   /     Sunny          │     \   /     Sunny          │     \   /     Sunny          │  _`/"".-.     Patchy rain po…│
│      .-.      39 °C          │      .-.      +45(49) °C     │      .-.      +43(46) °C     │   ,\_(   ).   +36(37) °C     │
│   ― (   ) ―   → 23-27 km/h   │   ― (   ) ―   → 26-30 km/h   │   ― (   ) ―   → 23-27 km/h   │    /(___(__)  ↘ 14-23 km/h   │
│      `-’      10 km          │      `-’      10 km          │      `-’      10 km          │      ‘ ‘ ‘ ‘  10 km          │
│     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │     ‘ ‘ ‘ ‘   0.1 mm | 69%   │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
Location: Meerut, Uttar Pradesh, 250001, India [28.9963296,77.7061915]

Follow @igor_chubin for wttr.in updates

In [ ]:
import requests

API_KEY = "8462b10dc5e94b938beed82ff1a17de8"  # Replace with your Weatherbit API key

def get_current_weather(city):
    url = f"https://api.weatherbit.io/v2.0/current?city={city}&key={API_KEY}"
    response = requests.get(url)
    
    if response.status_code == 200:
        data = response.json()
#         print(data)
        data = data['data'][0]
#         temperature = weather['temp']
#         description = weather['weather']['description']
#         print(f"Temperature: {temperature}°C")
#         print(f"Description: {description}")
        temperature = data["temp"]
        pressure    = data["pres"]
        humidity    = data["rh"]
        weather     = data["weather"]
        description = data["weather"]["description"]

        print(f"Temperature: {temperature}°C")
        print(f"atmospheric pressure (in hPa unit) = {pressure}")
        print(f"humidity (in percentage) = {humidity}")
        print(f"description = {description}")
    else:
        print("Error fetching weather data.")

# Example usage
city_name = "New Delhi"  # Replace with the desired city name
get_current_weather(city_name)
In [ ]:
import requests
from bs4 import BeautifulSoup
In [4]:
location = "Delhi"  # Replace with the location you want weather data for
url = f"https://www.google.com/search?q=weather+{location}"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")
location_element = soup.find("span", class_="BNeawe tAd8D AP7Wnd")
temperature_element = soup.find("div", class_="BNeawe iBp4i AP7Wnd")
condition_element = soup.find("div", class_="BNeawe iBp4i AP7Wnd").find_next("div", class_="BNeawe iBp4i AP7Wnd")
location = location_element.text
temperature = temperature_element.text
condition = condition_element.text
print("Location:", location)
print("Temperature:", temperature)
print("Condition:", condition)
Location: Delhi
Temperature: 42°C
Condition: 42°C
In [1]:
#Weather report
#Importing Beautifulsoup Library
from bs4 import BeautifulSoup
#importing requests module
import requests

#header user agent is a string allows the server to identify the O.S and application
# Change header accordingly as per OS like for window user-headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3'}

headers = {'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36'}#defining the weather function

def weather(city):
    # Replaces the space with + operator
    city=city.replace(" ","+")
    #requests and get function to get the information from the URL provided
    res=requests.get(f"https://www.google.com/search?q={city}&oq={city}"
                    f"&aqs=chrome.0.35i39l2j0l4j46j69i60.6128j1j7&sourceid="
                           f"chrome&ie=UTF-8",headers=headers)
    #searches the information from google
    print("Searching in google......\n")
    #Navigates on that particular website ,extract and store the data in soup object
    soup = BeautifulSoup(res.text,'html.parser')
    #gets the information of location 
    location = soup.select('#wob_loc')[0].getText().strip()
    #gets the information of time
    time = soup.select('#wob_dts')[0].getText().strip()
    #gets the desired information
    info = soup.select('#wob_dc')[0].getText().strip()
    #gets the weather information
    weather = soup.select('#wob_tm')[0].getText().strip()

    #prints location
    print("Data is found👇🏻")
    print(location)
    #prints time
    print(time)
    #prints info 
    print(info)
    #prints the weather in degree celcius
    print(weather+"°C")

    #enter the city name
print("Enter the city name")
city=input()

#Concatenating the city name and weather 
city=city+" weather"

#passing the city object to weather function
weather(city)
Enter the city name
New Delhi
Searching in google......

Data is found👇🏻
Weather
Tuesday, 3:00 pm
Mostly Sunny
42°C
In [ ]:
 
