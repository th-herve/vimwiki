# Python deploy flask app

Using an ovh ubuntu vps.
Based on this [video](https://www.youtube.com/watch?v=vfZgHX5ttsY&t=843s).

First ensure that `gunicorn` is in the project requirement:
```bash
# in the python venv
pip install gunicorn
pip freez > requirement.txt
```

1. ssh to the server
2. ensure that git is installed
3. create a `/var/www` directory
4. git clone the project
5. sudo apt install python3-pip python3-dev build-essential libssl-dev libffi-dev python3-setuptools6. Create venv (might need sudo): 
6. sudo apt install python3-venv
7. Create a venv
    > virtualenv venvName
8. source the venv: 
    > source ./venvName/bin/activate
9. install the requirement:
    > pip install -r requirements.txt
    
    > If getting an error `externaly manage env...`:
      > try installing with `./envName/bin/pip install -r requirements.text`
10. Install [caddy](https://caddyserver.com/docs/install#debian-ubuntu-raspbian)
11. Add a Caddyfile in the root directory with:
        ```json
        http://ip {
          reverse_proxy localhost:8000 
        }
        ```
12. Run `caddy stop` in the root directory
13. Then run `sudo caddy start` to run it with the new config file
14. Run the app with `gunicorn app:app` where the first app is the name of the python file with Flask object, and the second is the name of the Flask objectFlask object, and the second is the name of the Flask object.
