# Budibase FullCalendar
![image](https://github.com/diogenesbrussels/budibase-fullcalendar/assets/91942877/005fcde2-fda3-43a7-b8e4-de93c42fcd6b)


## Description
It's a component to implement fullcalendar in your budibase.

## Installation
To install the plugin for Budibase, follow these steps:

1. Copy the repository link ```https://github.com/diogenesbrussels/budibase-fullcalendar.git```.
2. Open Budibase and navigate to the "Plugins" section.
3. Click add plugin.
4. Select GitHub source.
5. Put the link in the URL section


<p>The plugin will be installed automatically.</p>

## Use

After installing the plugin for Budibase, you can start using it in your application. 
The plugin adds full calendar and functionality to the platform, allowing you to further customize your application.
You can use up to two data sources, the first source is mandatory. You can differentiate the two data sources in the calendar by changing the colors.

1. First add a data source
2. Add the calendar component inside the data source, you can search for FullCalendar
3.  Configure the data that will be used, up to 3 different data providers <p>![image](https://github.com/diogenesbrussels/budibase-fullcalendar/assets/91942877/53be63d7-cc3f-4c23-a5ec-d7582b098091)
</p>

## Features

1. Handle click on event
2. Map data that appears in the calendar
3. 3 different data groups by color
4. Set your language
5. Set start and end date to events

## Contributing

If you want to contribute to the development of the plugin, follow these steps:

1. Fork this repository.
2. Create a new branch with your changes: ```git checkout -b my-branch```
3. Make the desired changes and commit: ```git commit -m 'my changes```
4. Push your changes to your branch: ```git push origin my-branch```
5. Open a Pull Request to the original repository.4


## Instructions
To build this plugin run the following in your Budibase CLI:

```budi plugins --build```
You can also re-build everytime you make a change to your plugin with the command:

``` budi plugins --watch ```

## Known issues

- Refreshing data provider doesn't re-render the calendar accordingly

## Find out more about [Budibase](https://github.com/Budibase/budibase).
