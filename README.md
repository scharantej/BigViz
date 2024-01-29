# Flask App Design
---

## HTML Files
- **index.html**: This is the homepage of the web application. It will contain a description of the application and links to the two main features: the form for adding data to a BigQuery table and the data visualization page.
- **add_data.html**: This page will contain a form for adding data to a BigQuery table. It will include fields for the various columns in the table and a submit button.
- **visualize_data.html**: This page will allow users to visualize data from BigQuery tables. It will include a table view, a chart view, and a map view. Users will be able to select which table and which columns to visualize, and the page will dynamically update to show the selected data.

## Routes
### Main Routes
- `/`: This route will render the `index.html` page, the homepage of the application.
- `/add_data`: This route will render the `add_data.html` page, the form for adding data to a BigQuery table.
- `/visualize_data`: This route will render the `visualize_data.html` page, the page for visualizing data from BigQuery tables.

### Data Processing Routes
- `/submit_data`: This route will handle the submission of the data from the `add_data.html` form. It will validate the data and then send it to the BigQuery table using the appropriate API call.
- `/get_data`: This route will handle requests for data from BigQuery tables. It will accept parameters for the table name, the columns to retrieve, and the visualization type (table, chart, map). It will then query the BigQuery table and return the data in the requested format.

### Offline Sync Route
- `/sync_data`: This route will handle the synchronization of data between the web application and the BigQuery database. It will accept a list of changes (inserts, updates, deletes) and apply them to the BigQuery table. This route will be called periodically by the web application to keep the data in sync.

### Offline Installation Route
- `/install`: This route will handle the installation of the web application for offline use. It will generate a standalone version of the application that can be run without an internet connection. The generated application will include the necessary HTML, CSS, JavaScript, and Python files.

## Additional Considerations
- The application should use a responsive design to ensure it adapts to different screen sizes.
- The application should implement proper error handling and validation to ensure a user-friendly and stable experience.
- The application should include a caching mechanism to improve performance and reduce the number of requests to the BigQuery database.