File: src/components/RandomNumberDenerator/index.js 
import {Component} from 'react'

import './index.css'

class RandomNumberGenerator extends Component {
  state = {
    randomNumber: 0,
  }

  onGenerateRandomNumber = () => {
    const newRandomNumber = Math.ceil(Math.random() * 100)

    this.setState({randomNumber: newRandomNumber})
  }

  render() {
    const {randomNumber} = this.state

    return (
      <div className="app-container">
        <div className="random-number-generator-container">
          <h1 className="heading">Random Number</h1>
          <p className="description">
            Generate a random number in the range of 0 to 100
          </p>
          <button
            type="button"
            className="generate-button"
            onClick={this.onGenerateRandomNumber}
          >
            Generate
          </button>
          <p className="random-number">{randomNumber}</p>
        </div>
      </div>
    )
  }
}

export default RandomNumberGenerator

#index.css 
.app-container {
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: url('https://assets.ccbp.in/frontend/react-js/random-no-generator-bg.png');
  background-size: cover;
  height: 100vh;
}

.random-number-generator-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #ffffff;
  width: 80%;
  border-radius: 16px;
  border: 1px solid #e4ebf3;
  padding: 36px;
  box-shadow: 0px 4px 16px 0px #eaebed;
}

@media screen and (min-width: 768px) {
  .random-number-generator-container {
    width: 35%;
    max-width: 500px;
  }
}

.heading {
  text-align: center;
  color: #0b69ff;
  font-family: 'Roboto';
  font-size: 20px;
  font-weight: 700;
}

@media screen and (min-width: 768px) {
  .heading {
    font-size: 24px;
  }
}

.description {
  text-align: center;
  color: #333333;
  font-family: 'Roboto';
  font-size: 14px;
}

@media screen and (min-width: 768px) {
  .description {
    font-size: 18px;
  }
}

.generate-button {
  background-color: #0b69ff;
  color: #ffffff;
  font-family: 'Roboto';
  font-size: 12px;
  font-weight: 500;
  border-radius: 8px;
  border: none;
  padding-top: 8px;
  padding-left: 16px;
  padding-right: 16px;
  padding-bottom: 8px;
  margin-top: 14px;
  outline: none;
  cursor: pointer;
}

.random-number {
  color: #0b69ff;
  font-family: 'Roboto';
  font-size: 40px;
  font-weight: 700;
  margin-top: 24px;
}

@media screen and (min-width: 768px) {
  .random-number {
    font-size: 48px;
  }
}


File:src/components/App.js
import RandomNumberGenerator from './components/RandomNumberGenerator'

import './App.css'

const App = () => <RandomNumberGenerator />

export default App

#App.css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
