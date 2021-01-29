In your script ads @profile jsut before the function you want to profile:

@profile
def myfunction():

Then run the script as follows:

kernprof -v -l myscript.py