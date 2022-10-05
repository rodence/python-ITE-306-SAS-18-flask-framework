# python-ITE-306-SAS18-flask-framework
Python Flask Tutorial

### Step 1: Install Flask

  Open Terminal and type this commands:<br>
    
    python -m pip install --upgrade pip
    python -m pip install flask
    
### Step 2: Copy Sample Code

 * create a new file `app.py` and save it to a folder

```

    from flask import Flask
    from flask import jsonify
    from flask import request
    app = Flask(__name__)
    empDB=[
    {
    'id':'101',
    'name':'Dorry Britz',
    'title':'Technical Leader'
    },
    {
    'id':'102',
    'name':'Barbie Gurl',
    'title':'Software Engineer'
    }
    ]

    @app.route("/")
    def hello():
        return "Hello World!"

    @app.route('/empdb/employee/', methods=['GET'])
    def getAllEmp():
        return jsonify({'emp':empDB})

    @app.route('/empdb/employee/<empId>', methods=['GET'])
    def getEmp(empId):
        usr = [ emp for emp in empDB if (emp['id']==empId)]
        return jsonify({'emp':usr})

    if __name__ == '__main__':
        app.run()
				
```

* Open terminal and type the command:
		
		python -m flask run
		
#### Expected output:

	* Debug mode: off
	WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 	* Running on http://127.0.0.1:5000
	Press CTRL+C to quit
	127.0.0.1 - - [05/Oct/2022 21:52:18] "GET / HTTP/1.1" 200 -
	
	
copy the URL `http://127.0.0.1:5000/` and paste it in your preferred browser tab

#### The webpage will output:

	Hello World!

#### Try the other URL:


	http://127.0.0.1:5000/empdb/employee/
	http://127.0.0.1:5000/empdb/employee/101
	http://127.0.0.1:5000/empdb/employee/103
	
	
Now try to Press Ctrl+C to stop the server and try to paste the url on your browser
	
		http://127.0.0.1:5000/empdb/employee/
		
		
Credits: [jfnleabres2021](https://github.com/jfnleabres2021)
	
	


  
