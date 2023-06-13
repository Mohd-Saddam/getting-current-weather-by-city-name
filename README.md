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
Location: Meeru<img width="1318" alt="Screenshot 2023-06-13 at 3 55 30 PM" src="https://github.com/Mohd-Saddam/getting-current-weather-by-city-name/assets/50014573/c49ff886-e1dc-4d8f-8c60-a473834b8d38">
t, Uttar Pradesh, 250001, India [28.9963296,77.7061915]

 
