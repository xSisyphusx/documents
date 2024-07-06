---
description: To upload a video to the Video API, send a POST request to the API endpoint.
---

# Video

### API Endpoint

URL: [https://api.fivemerr.com/v1/media/videos](https://api.fivemerr.com/v1/media/videos)

### Headers

Include the `Authorization` header with your API key.

### Body

The request body should be a form-data object containing a file named `file`.

### Response

The response JSON body takes the following shape:

```json
{
    "id": 1,
    "uuid": "acdde24a-1a46-4880-9744-8b26b49f0460",
    "filename": "acdde24a-1a46-4880-9744-8b26b49f0460.mp4",
    "original_filename": "input.mp4",
    "mime_type": "video/mp4",
    "size": 137489,
    "hash": "ee828a888bf2c429b878306f8fc35bf9a7daff097b48a5cb7909a033f53274ed",
    "url": "https://fivemerr.com/files/videos/acdde24a-1a46-4880-9744-8b26b49f0460.mp4",
    "created_at": "2024-07-04T01:06:59.245622227+05:30",
    "updated_at": "2024-07-04T01:06:59.245622285+05:30"
}
```

### Example with Node.js (with Axios)

```javascript
const axios = require('axios');
const fs = require('fs');
const FormData = require('form-data');

// Load the image file
const filePath = '/path/to/your/video.mp4'; // Replace with your file path
const file = fs.createReadStream(filePath);

// Create a form data object
const form = new FormData();
form.append('file', file);

// Make the POST request
axios.post('https://api.fivemerr.com/v1/media/videos', form, {
  headers: {
    ...form.getHeaders(),
    'Authorization': 'YOUR_API_KEY' // Replace with your API key
  }
})
.then(response => {
  console.log(response.data.url);
})
.catch(error => {
  console.error(error);
});

```

### Example with Python

```python
import requests

# Load the image file
file_path = '/mnt/data/video.mp4' # Replace with your file path
files = {'file': open(file_path, 'rb')}

# Set the headers
headers = {
    'Authorization': 'YOUR_API_KEY', # Replace with your API key
    'Content-Type': 'multipart/form-data'
}

# Make the POST request
response = requests.post('https://api.fivemerr.com/v1/media/videos', files=files, headers=headers)

# Print the response
print(response.json())

```
