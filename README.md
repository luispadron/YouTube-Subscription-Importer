## Subscription Importer

Imports subscriptions from an xml/rss feed file into a youtube account. This is useful for transferring youtube subscriptions from one youtube account to another.

## Usage

1. Get the properly formatted xml file from the account you wish to transfer subscriptions from

	- Go to Subscriptions
	- Go to Manage Subscriptions
	- Scroll to end of page
	- Click Export Subscriptions next to Export to RSS readers

2. Get authenticated, since this requires access to your google account you must generate the correct `client_secrets.json` file

	- Create project in the [Developer Console](https://console.developers.google.com/apis/dashboard)
	- Next register for YouTube API, go to the project you just created and in the [Developer Console](https://console.developers.google.com/apis/dashboard). 
	- Go to the [API Library](https://console.developers.google.com/apis/library) and turn __YouTube Data API__ to __ON__.
	- Download JSON credentials, go to __Credentials__ if not created already, create one must be __OAuth 2.0__. Select the created credential and click on __Download JSON__.
	- Rename the downloaded JSON file to `client_secrets.json` and drag into this root directory, must be in the same folder as `subscribe.py`.
	
3. Make sure all required packages are installed before running

	To do this I recommend using a [virtual environment](https://virtualenv.pypa.io/en/stable/). 
	
	```bash
	$ virtualenv -p python3 env
	$ source env/bin/activate
	$ pip install -r requirements.txt
	
	```

4. Run the script
	
	To do this either drag the exported xml file from step 1 into this root directory and name it `subscriptions.xml` or run the script with this argument 
	
	```bash
	$ python3 subscribe.py --xml /path/to/xml/file.xml
	```
	
	
	
## Limitations

There is a request cap every few hours, I believe the cap is around ~70 subscriptions per few hours. So you may have to run the script several times before being able to fully import everything. I have not yet figured out a way around this.
