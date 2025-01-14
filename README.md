# Visao Coding Challenge

## Steps performed
- Setup local environment to run skeleton app (git, node & yarn modules required) +- 1h

Backend
- Create backend endpoint that returns the complete textures list 
    (select and implement new framework, convert json => object => json) +- 2h
- Weight, sort and filter textures +- 1h
- Adds basic unit tests +- 30m

FrontEnd 
- Search inspiration and setup project from scratch
- Setup Clean architecture, fetch and display textures as text +- 2h
- Create autocomplete and texture components natively +- 4h
- Misc improvements +- 1h

## How to run
Backend Setup using python with Falcon framework and waitress HTTP server (windows env)
- Move to backend directoty
- Install dependencies => 'pip install falcon falcon_params_verifier waitress'
- Start server => 'py -m main_server' (localhost:9090)
- Run unit tests => 'py -m unittest test_texture'

Frontend Setup
- Move to frontend directory
- Install dependencies with 'npm install'
- Run 'npm run dev' to start

## Improvements/TODO
- Unit tests in front for the clean archi
- Route /textures to get all textures to cleanly populate the autocomplete component data
- Input validation (just realized now while writing the feedback, lets say its not mandatory for this usecase :> )

## Inspiration
https://www.poliigon.com/textures

## Closing comments
I really enjoyed the exercise because it got me back into python and react and it's been a while.
For that reason, I realise that I was not as efficient as I would have liked.
To be honest, I spent most of the time doing research on how to implement stuff since I'm not that familiar with react.
Yet, even though it took me some time and it has flows, I still like the result from a non-expert point of view, I felt like I learned quite fast.
I know it's overkill but I wanted to try the clean architecture in react and it seems fine.
Also I was not completely sure about the insctructions so I improvised and implemented two different flows:
- Search component displays textures names on input in the search results.
- Call on input change displays suggestions based on searchTerm as Texture Component below the search component.

Overall I'd say it took me a bit over 12 hours but again, I spent more time searching and learning than implementing.

---

## Instructions
Design an API(backend) which serves suggestions of textures and a web page(frontend) 
which includes an autocomplete component to search them.
We have provided you with a skeleton React/Typescript project(frontend folder)
and another empty project(backend folder) which only includes a JSON data file for the textures.

1. Get your environment set up.
   - [Fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) this repo
   - Make sure node.js and yarn are installed for the frontend project
2. For the code:
   - We are looking for:
     - A finished product that meets the specs
     - Code readability and simplicity
     - Best practices around React components, frontend styling and backend apis
     - You to showcase your skill
   - Please don't:
     - Reach for any external UI components. We want to see you build.
   - Feel free to:
     - Create additional React components
     - Use any npm packages that are not UI component libraries(MUI, AntD, Bootstrap, etc...)
     - You can take as long as you like to complete this project
     - Inspire yourself from the web(dribbble, pinterest, etc...) to deliver a beautiful UI.
Make sure to reference it in your pull request. 
but we'd like you to keep track of much time you spend
3. Once finished, push your changes and open a pull request with:
   - How much time you spent
   - Any thoughts or extra context you want to provide about your code
   - Any thoughts or reflections you have about the project requirements

### Backend
Design an API endpoint that provides autocomplete suggestions for many textures.
- Setup the backend project
  - Provide the information to run it in the readme. Package installation, start command, port, etc...
  - Use either Python(what we use in our backend) or node.js as the language of choice
  - Use the backend framework of your choice
- Create an API endpoint must be exposed at `/textures/suggestions`
  - Use a query string parameter to pass the search term
  - Use a query string parameter to provide a limit of items that can be suggested
  - Based on the search term, 
use your imagination to apply a weight/score to find the best possible matches 
to find the best suggestions possible 
  - Should return a JSON response with an array of suggested textures
    - The suggestions should be sorted by descending weight(best match)
    - Return the number of suggestions corresponding to the limit parameter provided
    - Should follow this format
    ```
    [
      {
      "name": "Rustic Metal Texture",
      "description": "This free 3D texture features a rustic metal look, perfect for industrial scenes and settings.",
      "thumbnail_url": "https://example.com/textures/rustic_metal.jpg"
      }
    ]
    ```

### Frontend
Design an autocomplete component which and will show suggested textures
- As text is being typed into the component's input, a list of textures should render above/below it
- Suggestions must fetched from the api you designed
- Limit the number of suggestions fetched. For example, only show 5 items in the suggestion box.
- Suggested textures should contain the thumbnail, the name and part of the description
- The list items should be selectable by mouse click or hitting the enter key.
- The list of suggestions should NOT show when the input is less than two characters.
- Display a message when no suggestions are found
- The design should be mobile friendly