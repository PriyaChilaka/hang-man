
# Hangman
This project was bootstrapped with Create React App.

In the game, a random word has been selected and kept secret from the player, it is shown only as a
series of blanks where the letters should be (usually represented by ‘_’). The player must then guess
letters in turn; if they guess correctly, the blanks representing that letter are replaced with the letter
itself, but if they guess incorrectly, the player moves one step closer to &#39;hangman&#39;. Once the player
has successfully guessed every letter in the word, they win the game. However, if they make 8
incorrect guesses they lose and the word is revealed.


## API Reference

#### Get all items

```http
https://api.api-ninjas.com/v1/randomword
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `EiHx0QkczOSu3VwiaBCYKg==YYMmLnrf66pTTqVn` | `string` | **Required**. Your API key |

#### Get randomword



## Acknowledgements

 - https://facebook.github.io/create-react-app/docs/code-splitting
 - https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify

## Demo

npm start
Runs the app in the development mode.
Open http://localhost:3000 to view it in your browser.

The page will reload when you make changes.
You may also see any lint errors in the console.

npm test
Launches the test runner in the interactive watch mode.
See the section about running tests for more information.

npm run build
Builds the app for production to the build folder.
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.
Your app is ready to be deployed!

See the section about deployment for more information.

npm run eject
Note: this is a one-way operation. Once you eject, you can't go back!

If you aren't satisfied with the build tool and configuration choices, you can eject at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except eject will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use eject. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

Learn More
You can learn more in the Create React App documentation.

To learn React, check out the React documentation.

Code Splitting
This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

Analyzing the Bundle Size
This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

Making a Progressive Web App
This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

Advanced Configuration
This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

Deployment
This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

npm run build fails to minify
This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify


## 🚀 About Me
I'm a full stack developer, Enthusiastic person to learn new technologies grasping new techniques.Friendly nature very communicative with other people . Good Colloboration with co-workers.


## 🔗 Links
 - https://www.linkedin.com/in/priya-kolukuluri-38247b47
 - https://github.com/PriyaChilaka

## Related
- github.com/PriyaChilaka/hangman  without API only native React

## Lessons Learned

 - Google the Examples using random words
 - Watched youtube projects regarding Hangman
 

## Installation

Install hang-man with npm

```bash
  npx create-react-app hangman-app
  cd hangman-app
  npm start
  
```
    
## Usage/Examples

```React JS
import React,{useState,useEffect} from 'react';
import Header from './components/Header';
import Figure from './components/Figure';
import WrongLetters from './components/WrongLetters';
import Word from './components/Word';
import './App.css';
import Popup from './components/Popup';
import Notification from './components/Notification';


const words = ['application', 'programming', 'interface', 'wizard'];

let selectedWord = words[Math.floor(Math.random() * words.length)];


function App() {
  const [playable,setPlayable] = useState(true);
  const [correctLetters,setCorrectLetters] = useState([]);
  const [wrongLetters,setWrongLetters] = useState([]);
  const [showNotification,setNotification] = useState(false);
useEffect(() => {
const handleKeydown = event => {
  const {key,keyCode} = event ;
  
    if (playable && keyCode >= 65 && keyCode <= 90) {
      const letter = key.toLowerCase();

      if (selectedWord.includes(letter)) {
        if (!correctLetters.includes(letter)) {
          setCorrectLetters(currentLetters => [...currentLetters,letter])

          
        } else {
          //showNotification();
        }
      } else {
        if (!wrongLetters.includes(letter)) {
          setWrongLetters(wrongLetters =>[...wrongLetters,letter])
          
        } else {
          //showNotification();
        }
      }
    }
  }

window.addEventListener('keydown',handleKeydown);

return ()=> window.removeEventListener('keydown',handleKeydown);
},[correctLetters,wrongLetters,playable]

,[]);

  
  return (
    <>
     <Header></Header>
       <div className='game-container' >
        <Figure  wrongLetters={wrongLetters}/>
        <WrongLetters wrongLetters={wrongLetters} />
        <Word selectedWord={selectedWord} correctLetters={correctLetters}/>
        <Popup />
        <Notification />
       </div>
    </>
  );
}

export default App;
## Tech Stack

**Client:** React, Redux, CSS

Using Backend API


## 🛠 Skills
ReactJS, JavaScript,Java,.net,VueJS,WordPress CMS

