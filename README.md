# smartcarAPIConnect
Building a System Utilizing Flask Web Framework and Smartcar API

The provided Python code sets up a web application using the Flask framework and integrates the Smartcar API for authentication and accessing vehicle information. Let me walk you through the main components and their functionalities:

https://smartcar.com/

![samrtcarapi](https://github.com/louisbyun/smartcaAPIConnect/assets/55345082/0e94a45f-5fec-4c58-bcba-b09a3265e2d7)


Flask Setup:

Flask is a web framework for Python.
A Flask application is created, and a secret key is set for managing user sessions securely.
Smartcar API Configuration:

Smartcar API credentials (client ID, client secret, and redirect URI) are configured.
An instance of the Smartcar AuthClient is created using the configured credentials.
Flask Routes:

Several routes are defined to handle different parts of the application:
'/': Renders the main page using the index.html template.
'/login': Initiates the Smartcar authentication process by redirecting to the Smartcar authorization URL.
'/callback': Handles the callback from Smartcar after a successful authentication and stores the access token in the user session.
'/dashboard': Displays the dashboard with vehicle information (requires authentication).
Vehicle Information Retrieval:

The get_vehicle_info function is a placeholder for the code that would retrieve vehicle information using the Smartcar API. The actual implementation would involve making requests to the Smartcar API, such as calling the /vehicle endpoint.
Application Execution:

The script runs the Flask application in debug mode when executed directly.
Overall, this code provides a foundation for building a web application that allows users to log in with Smartcar and view a dashboard with vehicle information. The actual vehicle information retrieval logic needs to be implemented in the get_vehicle_info function, utilizing the Smartcar API.

SHA-256 encryption part has been added.

import hashlib

def sha256_hash(data):
     return hashlib.sha256(data.encode()).hexdigest()

# Example Usage in a Route
@app.route('/some_route')
def some_route():
     user_data = 'example_user_data'
     hashed_data = sha256_hash(user_data)
     # Use hashed_data for storing or comparing purposes
