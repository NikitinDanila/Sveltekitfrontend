# FrontEnd Sveltekit and Backend Fast API project

# Backend using Fast API
Backend consists of a single GET function. That function incorporates a getmessage function that randomly generates int in range of 0 to 99, converts it to string and adds a message in a "Hello XX" format where XX is a random number.
CORSMiddleware library is added in order to handle CORS errors and run both frondend and Backend on localhost.

# Frontend using Sveltekit
Front end utilize a generic project layout to which two a button module is attached that handles button click and an input window which shows the message received from the backend.

# Installation guide
Download the zip file in code tab, unzip it at prefferable directory and run following commands via cmd in the chosen directory.                                                                                                                                                                                                                                                    

Fast API installation and uvicorn server startup
pip install "fastapi[all]"
uvicorn main:app --reload

Sveltekit installation and startup
npm run dev -- --open
