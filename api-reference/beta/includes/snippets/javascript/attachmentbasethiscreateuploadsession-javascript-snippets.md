---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const uploadSession = {
  attachmentInfo: {
    '@odata.type': 'microsoft.graph.attachmentInfo',
    attachmentType: 'file',
    name: 'flower',
    size: 3483322
  }
};

await client.api('/me/todo/lists/AAMDiFkfh=/tasks/AAMkADliMm=/attachments/createUploadSession')
	.version('beta')
	.post(uploadSession);

```