# LB Phone

## Set your config to "Custom".

Config.UploadMethod.Video = "Custom"
Config.UploadMethod.Image = "Custom"
Config.UploadMethod.Audio = "Custom"

## Create a MEDIA API key and add it below to all 3.

API_KEYS = {
    Video = "PUT MEDIA API HERE",
     Image = "PUT MEDIA API HERE",
     Audio = "PUT MEDIA API HERE",
}

## On UploadMethods at Custom. Replace for this

Custom = {
        Video = {
            url = "https://api.fivemerr.com/v1/media/videos",
            field = "file", -- The field name (formData)
            headers = { -- headers to send when uploading
                ["Authorization"] = "API_KEY"
            },
            error = {
                path = "success", -- The path to the error value (res.success)
                value = false -- If the path is equal to this value, it's an error
            },
            success = {
                path = "url" -- The path to the video file (res.url)
            },
        },
        Image = {
            url = "https://api.fivemerr.com/v1/media/images",
            field = "file", -- The field name (formData)
            headers = { -- headers to send when uploading
                ["Authorization"] = "API_KEY"
            },
            error = {
                path = "success", -- The path to the error value (res.success)
                value = false -- If the path is equal to this value, it's an error
            },
            success = {
                path = "url" -- The path to the image file (res.url)
            },
        },
        Audio = {
            url = "https://api.fivemerr.com/v1/media/audios",
            field = "file", -- The field name (formData)
            headers = { -- headers to send when uploading
                ["Authorization"] = "API_KEY"
            },
            error = {
                path = "success", -- The path to the error value (res.success)
                value = false -- If the path is equal to this value, it's an error
            },
            success = {
                path = "url" -- The path to the audio file (res.url)
            },
        },
    },

Restart your phone script and you're all set!
