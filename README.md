# weatherApi
#This is a python Automation code. I used OpenWeatherMap API to fetch weather information for a given city. 
import requests
API_KEY="6c30a7152a8484a1bf576304df72830b"
BASE_URL="http://api.openweathermap.org/data/2.5/weather"
CITY=input("enter the req city: ")
request_url=f"{BASE_URL}?appid={API_KEY}&q={CITY}"
response=requests.get(request_url)
if  response.status_code==200:
    data=response.json()
    print(data['weather'][0]['description'])
    print(str(round(data['main']['temp']-272.15,2))+' Celsius')
else:
    print("an error has occured")
