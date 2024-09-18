Yes, I’ve had experience with all three of these tasks in WordPress. Here’s a breakdown:

### Custom Gutenberg Block
Creating a custom Gutenberg block involves several steps. Here’s a general overview:

- `cd your_project_dir/wp-content/plugins/`
- `npx @wordpress/create-block@latest Custom-Gutenberg-Block-wipro-task`
- `cd custom-Gutenberg-Block-wipro-task`
- open wp-admin 
- go to plugin and activate the plugin
- open the plugin and see the block in the editor
- add the block and see the output

### WordPress Theme Development
I’ve developed WordPress themes from scratch. One notable challenge was ensuring cross-browser compatibility and responsiveness. Here’s how I addressed it:

1. Challenge: Making sure the theme looks and functions correctly across different browsers and devices.
2. Solution: 
   - Utilized CSS Grid and Flexbox for responsive layouts.
   - Used tools like BrowserStack to test on various browsers.
   - Ensured that the theme adhered to best practices in web accessibility and performance.

### REST API Endpoint Development
#### To create a REST API in WordPress, follow these steps:

- Create a Plugin: First, create a new plugin to house your custom REST API code.
- Register the REST Route: Use the register_rest_route function to define your custom endpoint.
- Create Callback Functions: Define the callback functions that will handle the requests to your endpoint.
- Test the API: Use tools like Postman or cURL to test your new REST API endpoint.

#### Step-by-Step Plan
- Create a new directory for your plugin in the wp-content/plugins directory such as my-custom-api.
- Create a new PHP file in the plugin directory (inside my-custom-api dir.) such as my-custom-api.php.
- Add the following code to the my-custom-api.php file to create a new REST API endpoint:
    ```php
    <?php
    /*
    Plugin Name: My Custom API for Wipro task
    Description: A custom REST API for WordPress.
    Version: 1.0
    Author: Your Name
    */

    // Hook to initialize the REST API
    add_action('rest_api_init', function () {
        register_rest_route('myplugin/v1', '/data', array(
            'methods' => 'GET',
            'callback' => 'myplugin_get_data',
        ));
    });

    // Callback function to handle the request
    function myplugin_get_data($request) {
        $data = array(
            'message' => 'Hello, this is your custom API response!',
            'status' => 'success'
        );
        return new WP_REST_Response($data, 200);
    }
    ```

- Go to the WordPress admin dashboard, navigate to Plugins, and activate "My Custom API for Wipro task".

### Test the API

- Use a tool like Postman or cURL to send a GET request to your custom API endpoint:
    - http://yourdomain.com/wp-json/myplugin/v1/data

- You should receive a JSON response:
```json
{
    "message": "Hello, this is your custom API response!",
    "status": "success"
}
```