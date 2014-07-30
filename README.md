Yahoo-Weather
=============

PHP class that uses the Yahoo! Weather API.

###Use

The class used as a parameter **WOEID** of Yahoo! GeoPlanet and temperature **unit**

```
include "yahoo-weather.class.php";
  
$weather = new YahooWeather('349867','c');

if($weather->is_found)
{
	$current = $weather->getCondition();

	echo $weather->getCity()." ". $current['temp'] . "&deg;". $weather->getUnit();
	
	foreach($weather->getForecast() as $day)
	{
		echo "Day: ".$day["day"] ." | ";
		echo "Date: ".$day["date"] ." | ";
		echo "High: ".$day["high"] ." | ";
		echo "Low: ".$day["low"] ." <br />";
	}
}
```

Results

```
Rancagua 13°C
Day: Wed | Date: 30 Jul 2014 | High: 21 | Low: 11 
Day: Thu | Date: 31 Jul 2014 | High: 16 | Low: 10 
Day: Fri | Date: 1 Aug 2014 | High: 23 | Low: 11 
Day: Sat | Date: 2 Aug 2014 | High: 17 | Low: 8 
Day: Sun | Date: 3 Aug 2014 | High: 16 | Low: 5
```

###Get **WOEID** of Yahoo! GeoPlanet
Link http://jcabezas.cl/proyectos/get-woeid/