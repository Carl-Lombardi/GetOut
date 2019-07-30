## Get Out- https://carl-lombardi.github.io/GetOut/ (Site) https://github.com/Carl-Lombardi/GetOut (Repo)
Our project is a new app which will be indispensable to the business traveler and the weekend getaway types alike. Have you ever traveled to a new city and wondered just what there is to do? This app combines the power of EventBrite and Open Weather into a user-friendly experience which allows a person to find the weather and a list of activities in any city in the United States with just a few clicks. 

## Why Get Out?
Traveling is a hassle. Between getting your items packed and getting on the road or to the airport, it's never an easy experience. One of the biggest questions people have is "What will the weather be in the new city"? Often behind that is a question about what there is to do in the new city that isn't a tourist attraction or the typical restaurant. Get Out changes the stress of travel in a new city to a fun experience by helping a traveler streamline their packing and dress for any activity they may want to pursue. 

## Get Out uses Materialize 
Materialize is a modern responsive CSS framework based on Material Design by Google per their website. It was used to display the weather information in a clear, concise manner which allows the end user to see weather at three-hour intervals in a carousel. 

## Features 
Get Out features a clean UI with an end user experience desired by many and achieved by few. No additional instructions are on screen to create confusion for the end user other than basic needed instructions for app functionality. A business user traveling to multiple cities can find the weather for each leg of their trip over a seven-day period, and even find some fun activities for after a meeting. For the weekend getaway types or even for those who are looking for fun activities in their home city, Get Out will make life simpler and allow users more time for fun. 

## Code Example
 function runWeatherAJAX(divId) {
    $.ajax({
      url: weatherQueryURL,
      method: "GET"
    }).then(function (weatherResponse) {
      $("#eventContainer").append("<div class = 'DestroyMe' id = AwesomeNewDiv" + divId + ">");
      $("#AwesomeNewDiv" + divId).append("<h3>5-Day Weather Forecast for " + weatherResponse.city.name + "</h3>");
      $("#AwesomeNewDiv" + divId).append("<div class = 'carousel' id=CarouselDiv" + divId + ">");

      for (i = 0; i < (weatherResponse.list).length; i++) {
        counterCarousel++;
        $("#CarouselDiv" + divId).append("<div class = 'carousel-item cyan white-text' href='#' id=CarouselItem" + counterCarousel + ">");
        $("#CarouselItem" + counterCarousel).append("<p class='white-text'>" + weatherResponse.list[i].dt_txt + "</p>");
        $("#CarouselItem" + counterCarousel).append("<p><img src = 'http://openweathermap.org/img/w/" + weatherResponse.list[i].weather[0].icon + ".png' class='floatLeft' alt='WeatherIcon'></p>");
        $("#CarouselItem" + counterCarousel).append("<h5>" + weatherResponse.list[i].weather[0].description + "</h5>");
        $("#CarouselItem" + counterCarousel).append("<p class='white-text'>Temp= " + weatherResponse.list[i].main.temp + "°F</p>");
      }
      $('#CarouselDiv' + divId).carousel();
    }, function () {
      console.log("Error, weather ajax call city not found");
      alert("City Not Found, Click 'clear all searches' button to proceed");
    });
  }

  The above code is the AJAX Call which calls the Open Weather API.

## Installation
No outside software is needed to use Get Out. Our application is web based and can be accessed by anybody at any time. 

## How To Use
The beauty of Get Out is its simplicity. Via clearly defined instructions, end users will enter the beginning and end of their trip (or weekend!), their city and an activity they would like to pursue. Once the app is provided the needed information, it goes to work finding weather from Open Weather and a list of culled activities from EventBrite to display to the user. 

## Issues and Solutions
Get Out is an app in transition with multiple solutions both currently and in the future pending potential funding sources. One issue that has been discussed is the limiting of weather reports to one week from the current date. While Free use API’s have been used in the app as currently constructed, there are limits to data being used. One solution may be to pay for API data which would allow the app to function further into the future allowing the end user more flexibility in choosing dates for their trip. Another possible expansion could be for linking to airline websites or other travel sites (railroads for example) to allow Get Out to be a full use app integrating weather, activities and travel to allow users to plan every aspect of their trip from beginning to end.  Further expansion may also link to hotels as well, allowing an “one-stop-shopping” experience for all forms of travel and planning. Whether it’s for business or pleasure with family, friends or a significant other, Get Out has the possibility to go beyond the simplicity as currently constructed and change the way travelers and even homebodies plan activities in their city.

## Credits
Get Out is an app combining the talents of Nick Schaefer, Keishawn Johnson, and Carl Lombardi. 
