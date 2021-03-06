---
category: features
---

# Image upload

Inserting images into content created with CKEditor is a very common task. CKEditor 5 introduced a totally new way of handling images, with strong focus on the end user experience. The goal is to make this an effortless and intuitive task.

In a properly configured editor, there are several ways for the end user to insert images:

* Pasting it from the clipboard.
* Dragging a file from the file system.
* Selecting it through a file system dialog.
* Selecting it from a media management tool in your application.

Excluding the last option, all other ways require the image to be uploaded to a server, which will be the one responsible for providing the image URL used by CKEditor to display the image in the document.

The image insertion, therefore, is made of a few steps, which are transparent to the end user:

1. The user inserts an image.
2. A temporary image (placeholder) is inserted.
3. The image is being uploaded.
4. The server returns the image URL.
5. The temporary image is replaced with the definitive one.

<!-- TODO [ Drawing: workflow ( User Inserts Image ) -> ( Temporary Image Inserted ) -> ( Image Uploaded ) -> ( URL Returned ) -> ( Temporary Image Replaced with Definitive ) ] -->

To make the above process possible, an image upload plugin must be available. Such plugin will handle both the upload and URL returning steps in the above workflow.

## Responsive images

Another great feature introduced with CKEditor 5 is the ability to have responsive images in the content. With a single image upload, several optimized versions of that image are created after upload, for different size of displays. All this is totally transparent to the end user who uploaded the image.

Be sure to use image upload plugins with support for responsive images to enjoy this important additional benefit. [Easy Image](#Easy-Image) has support for responsive images out of the box, too.

## Easy Image

To make enabling image upload in CKEditor 5 a breeze, by default all builds include the {@link module:easy-image/easyimage~EasyImage `EasyImage` plugin}, which integrates with the Easy Image service provided by [CKEditor Cloud Services](https://ckeditor.com/ckeditor-cloud-services/). Enabling it is straightforward and the results are immediate:

<info-box warning>
	CKEditor Cloud Services are in private beta. [Contact us](https://ckeditor.com/contact/) to learn more.
</info-box>

1. Create an account in CKEditor Cloud Services (CS).
2. Create an API key in your CS account.
3. Create a security token entry point in your application.
4. Configure CKEditor to use the security token entry point:

	```js
	ClassicCreator
		.create( document.querySelector( '#editor' ), {
			cloudServices: {
				token: 'token-retrieved-from-the-cs-token-server'
			}
		} )
		.then( ... )
		.catch( ... );
	```

This is all. At this point, image upload will be automatically enabled in your application.

## What's next?

See the {@link features/image Image feature} guide to learn more about handling images in CKEditor 5.
