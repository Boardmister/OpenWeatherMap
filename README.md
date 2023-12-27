# OpenWeatherMap
Fetch and display the current weather forecast using the OpenWeatherMap API.
import requests

api_key = 'your_openweathermap_api_key'
city = 'London'
api_url = f'http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}'

response = requests.get(api_url)

if response.status_code == 200:
    weather_data = response.json()
    temperature = weather_data['main']['temp']
    description = weather_data['weather'][0]['description']
    print(f"Current Weather in {city}: {description}, Temperature: {temperature}°C")
