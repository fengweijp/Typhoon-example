spring-objective-c-example
==========================

An example application built with spring-objective-c. Features: 

* Returns weather reports from a remote cloud service
* Caches weather reports locally
* Stores the cities that the user is interested in receiving reports for. 
* Can use metric or old-style units. 

### The Assembly
```xml

<assembly xmlns="http://jasperblues.github.com/spring-objective-c/schema/assembly"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://jasperblues.github.com/spring-objective-c/schema/assembly
          http://www.appsquick.ly/schema/assembly.xsd">

    <component class="PFWeatherClientBasicImpl" key="weatherClient">
        <description>
            This is component retrieves weather reports from the cloud-service.
        </description>
        <property name="serviceUrl" value="http://free.worldweatheronline.com/feed/weather.ashx"/>
        <property name="apiKey" value="$YOUR_API_KEY_HERE$"/>
        <property name="weatherReportDao" ref="weatherReportDao"/>
    </component>

    <component class="PFWeatherReportDaoFileSystemImpl" key="weatherReportDao">
        <description>
            This class is responsible for caching retrieved reports to the device for later usage.
        </description>
    </component>

    <component class="PFCityDaoUserDefaultsImpl" key="cityDao">
        <description>
            This class is responsible for saving and retrieving cities the user wants reports for.
        </description>
    </component>

</assembly>


```

### The App ('scuse the dev's designs). 

<img src="https://github.com/jasperblues/spring-objective-c-example/blob/gh-pages/weather-report.png"/>
<img src="https://github.com/jasperblues/spring-objective-c-example/blob/gh-pages/cities-list.png"/>
<img src="https://github.com/jasperblues/spring-objective-c-example/blob/gh-pages/add-city.png"/>

