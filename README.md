# Expo weather icons

Wonderful project [weather-icons](https://github.com/erikflowers/weather-icons) by Erik Flowers.

## Process

Clone this repo and add selection.json and weather-icons.ttf into the folder of choice (in my example under assets/weatherIcons). You want to create icon set from this font and then load that font to be able to use it.

- Create icon set with a name you want. In this example it will be called WeatherIcon (font will be called WeatherIconFont):
  ```
  export const WeatherIcon = createIconSetFromIcoMoon(
     require("@/assets/weatherIcons/selection.json"),
     "WeatherIconFont",
     "weather-icons.ttf"
  );

  ```
- Import that font in your component with useFonts():

  ```
  const [fontsLoaded] = useFonts({
      WeatherIconFont: require("@/assets/weatherIcons/weather-icons.ttf"),
  });

  if (!fontsLoaded) {
  return null;
  }

  ```

- Use it as icon:
  ```
  <WeatherIcon name="wi-raindrop" size={20}/>
  ```
