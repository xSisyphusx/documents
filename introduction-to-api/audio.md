---
description: To upload an audio to the Audio API, send a POST request to the API endpoint.
---

# Audio

### API Endpoint

URL: [https://api.fivemerr.com/v1/media/audios](https://api.fivemerr.com/v1/media/audios)

### Headers

Include the `Authorization` header with your API key.

### Body

The request body should be a form-data object containing a file named `file`.

### Response

The response JSON body takes the following shape:

```json
{
    "id": 1,
    "uuid": "54812bad-eb9a-4ad0-bf90-412185a27e74",
    "filename": "54812bad-eb9a-4ad0-bf90-412185a27e74.mp3",
    "original_filename": "joe_japanese.mp3",
    "mime_type": "audio/mpeg",
    "size": 307722,
    "hash": "4dfdfa634076d6f6abf3b84486c7c2940c1a8d86e60535c4aaca2692fbb6d650",
    "url": "https://fivemerr.com/files/audios/54812bad-eb9a-4ad0-bf90-412185a27e74.mp3",
    "created_at": "2024-07-04T01:04:27.772178312+05:30",
    "updated_at": "2024-07-04T01:04:27.772178364+05:30"
}
```

### Example with Node.js (with Axios)

```javascript
const axios = require('axios');
const fs = require('fs');
const FormData = require('form-data');

// Load the image file
const filePath = '/path/to/your/audio.mp3'; // Replace with your file path
const file = fs.createReadStream(filePath);

// Create a form data object
const form = new FormData();
form.append('file', file);

// Make the POST request
axios.post('https://api.fivemerr.com/v1/media/audios', form, {
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
file_path = '/mnt/data/image.mp3' # Replace with your file path
files = {'file': open(file_path, 'rb')}

# Set the headers
headers = {
    'Authorization': 'YOUR_API_KEY', # Replace with your API key
    'Content-Type': 'multipart/form-data'
}

# Make the POST request
response = requests.post('https://api.fivemerr.com/v1/media/audios', files=files, headers=headers)

# Print the response
print(response.json())

```

### Support Audio Types

If you need any other added, let us know.

* **MPEG** - `.mpeg`
* **WAV** - `.wav`
* **OGG** - `.ogg`
* **AAC** - `.aac`
* **FLAC** - `.flac`
* **WMA** - `.wma`
* **AIFF** - `.aiff` or `.aif`
* **PCM** - `.pcm`
* **AMR** - `.amr`
