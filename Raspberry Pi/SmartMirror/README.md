# Smart Mirror

### Prerequisite
1. Git installed (perferablly git a CLI)
2. node installed (perferablly 14.X version)

### Installing node (mac)
1. Install [homebrew](https://brew.sh/) using the following command `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
2. Install node using `brew install node` in the terimal 

### Install node (RPI / debian based linux)
The perfered version of node for this project is [v14.x here](https://github.com/nodesource/distributions/blob/master/README.md#debinstall) but the others should work install.
1. open the terminal and run `curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -` 
2. upon completion run `sudo apt-get insatll -y nodejs`


### Install node (Windows)
1. Go to [this website](https://nodejs.org/en/download/) to install the windows nodejs installer


### Verify node is installed (cross platform)
1. in a terminal run `node -v` as well as `npm -v` these should both repond with version of their respective software package

### install git (Windows)
1. Go to [this link](https://git-scm.com/downloads) and follow instructions to download git bash
2. Make sure to choose `nano` as the default editor for commits
3. NOTE: if after running `git push` the terminal hangs make sure it did not prompt you for your credentials and if it didn't then reinstall git bash but use a different credentials manager. 


### Install git (Mac)
1. Mac should come with git installed but if it does not follow the first step for installing node on mac (installing homebrew)
2. Then run in the terminal `brew install git`


### Setup for both Local and RPI development 
1. Go to [the Github repo](https://github.com/GIP2000/SmartMirror) and fork the repository
2. Clone the now forked repository to local computer 
2. Follow instructions for startup


### Useful Resources
1. [React Tutotiral](https://www.youtube.com/watch?v=hQAHSlTtcmY&ab_channel=WebDevSimplified)
2. [Spotify API with react Tutorial](https://www.youtube.com/watch?v=Xcet6msf3eE&ab_channel=WebDevSimplified)
3. [Axios used for HTTP requests](https://www.npmjs.com/package/axios)


### Key concepts
1. Useing HTTP requests (with axios)
2. JS promises
3. JSX and JS interactions (using `{}` inside of JSX statment)
4. useState in react and why we need it (in order to make our components stateful as well as update when the variables change)
5. useEffect in react and why we need it (in order to allow side effects, run componentDidMount, componentUnMount (i.e. cleanup), as well as onChange listners for state variables)
6. What is CORS 
7. Server side running of HTTP requests do to CORS issues. (making a new endpoint in the backend side of the code in order to call it later to avoid cors issue)

