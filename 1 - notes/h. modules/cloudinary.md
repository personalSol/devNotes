---
status: newBorn
related-links: 
created: 2025-06-02T08:51
updated: 2025-06-06T15:48
---
---


- an online service where we upload files
- this gives us link which then we use to show resources ( don't know how we show resources from url )
- first we have to config it with credentials which we get from the cloudinary website
- then we use it using uploader.upload
- we have also used [[fs#🔹 fs unlinkSync]] to unlink/delete the file after successsful or unsuccessful completion of operation
- `response.url` is used to get the url to upload on database

```js
import { v2 as cloudinary } from "cloudinary";

// Configuration
cloudinary.config({
    cloud_name: process.env.CLOUDINARY_CLOUD_NAME,
    api_key: process.env.CLOUDINARY_API_KEY,
    api_secret: process.env.CLOUDINARY_API_SECRET
});

const uploadFileOnCloudinary = async (localFilePath) => {
    try {
        if(!localFilePath) return null;
        const response = await cloudinary.uploader.upload(localFilePath, {
            resource_type: auto,
        })

        //upload successful message
        console.log("File uploaded at", response.url);
        fs.unlinkSync(localFilePath); // removing the file as it's no longer needed in system
        return response;
    } catch (error) {
        fs.unlinkSync(localFilePath) // removed the locally saved temporary file as the upload got failed
        return null;
    }
}
```
