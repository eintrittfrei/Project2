# General Assembly Project 2

## Overview
This is a basic weather app which can be used to type in any location by city or country. It will present the current weather condition at that location. 

## Project Members
Ole Nascimento https://github.com/eintrittfrei
Emilie Sherrott https://github.com/emilesherrott

## Timeframe
48 hours 

## Project Brief:  

Build a React application that consumes a public API.
​
### Technical Requirements
* The app must consume a public API.
* Have several components.
* The app can have a router - with several "pages".
* Include wireframes - that you designed before building the app.
* Be deployed online and accessible to the public.
* You should use pair coding techniques.
​
## Technologies Used

* React
* React Router
* JavaScript (ES6)
* HTML5
* SASS
* CSS3
* Git
* GitHub
* VScode
* Google Fonts

## Weather App

![Screenshot 2021-08-16 at 14 47 18](https://user-images.githubusercontent.com/16645758/129566192-3e04bd2f-2a53-42f5-8747-4bb9bdef3a50.png)


## Deployed version

<a href="https://oleproject2.netlify.app/" target="_blank">Deployed Version</a>

## Installation
Clone or download the repo. In your terminal run the following commands: 

Install dependencies with 'yarn add' 
Run 'yarn start' in the terminal 

## Planning
This was a 48h hackathon challenge and we decided to create a basic weather app based on location information typed in by the user. We started by researching suitable public APIs and chose weatherapi.com because it is free to use and offers a large choice of weather information. We planned some basic wireframes for our project and started to write some pseudocode. We decided that one of us would be coding while we both were discussing what to do next based on our plan. 

## Process
First we set up a basic react application. We decided to make the API request first as this would likely take some time doing this for the first time. We used the documentation from weatherapp.com on how to make basic requests.  

First we used useEffect() and async/ await to make our request and set the weather data to state. We could see our weather data in the console.log using Chrome developer tools.

```javascript
useEffect(() => {
    const getData = async () => {
      try {
        const { data } = await axios.get(`https://api.weatherapi.com/v1/forecast.json?key=bc3268a2d36f4676922230553211606&q=${formSubmit}&days=1&aqi=yes&alerts=no`)
        setWeather(data)
      } catch (err) {
        console.log(err)
      }
    }
    getData()
  }, [formSubmit])

```

We now needed to create a basic form for the user to enter location information. We set the form information to state and passed this into the request url for the API request as a template literal. Now the weather information would be based on the user's location input. 

```javascript
const Home = () => {
  const [formData, setFormData] = useState({
    location: '',
  })
  const [formSubmit, setFormSubmit] = useState('')
  const [weather, setWeather] = useState('')

  const handleChange = (event) => {
    console.log(event.target.value)
    const newFormData = { ...formData, [event.target.name]: event.target.value }
    setFormData(newFormData)
  }
  const handleSubmit = (event) => {
    event.preventDefault()
    setFormSubmit(formData.location)
  }

```
In the next step we built out the weather information on the display page using the Bulma CSS framework. 
 
## Challenges
Getting data back from the API was challenging. We needed to pass in the location information and also our authentication key for the API which took some time to work out how to do this. 
Using Bulma as a CSS framework also presented a challenge as we had not used this framework before.
Reading documentation has helped to understand how to use both technologies. 

## Wins & Key Learning 
* How to make requests to a public API and display those on a user page. 
* How to use a CSS framework. 
* Pair coding was definitely a new experience and we learned a lot about how to pair code effectively. 

## Bugs

* The layout is slightly off. When displaying full weather inormation on a smaller screen the text goes beyhond the page boundaries. 

## Future Improvements 

* Showing extra information toggle on/ off. 
* Automated display of local weather based on user location information.



