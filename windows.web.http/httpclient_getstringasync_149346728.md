---
-api-id: M:Windows.Web.Http.HttpClient.GetStringAsync(Windows.Foundation.Uri)
-api-type: winrt method
---

<!-- Method syntax
public Windows.Foundation.IAsyncOperationWithProgress<string, Windows.Web.Http.HttpProgress> GetStringAsync(Windows.Foundation.Uri uri)
-->

# Windows.Web.Http.HttpClient.GetStringAsync

## -description
Send a GET request to the specified Uri and return the response body as a string in an asynchronous operation.

## -parameters
### -param uri
The Uri the request is sent to.

## -returns
The object representing the asynchronous operation.

## -exceptions
### E_INVALIDARG

The *uri* parameter was a **null** reference (**Nothing** in Visual Basic).

## -remarks
This operation will not block. The returned [IAsyncOperationWithProgress(String, HttpProgress)](../windows.foundation/iasyncoperationwithprogress_2.md) object will complete after the whole response body is read.

The [HttpClient](httpclient.md) class is often used by an app to download and then parse text. It is possible that the character encoding specified in the **Content-Type** header by an HTTP server does not match the character encoding of the HTTP response body (the XML encoding in an XML document, for example). One way to use [HttpClient](httpclient.md) with text is to call the [GetStringAsync](httpclient_getstringasync.md) method and pass the returned string to the text parser. However, this can result in errors if the **Content-Type** is not a type expressible as a string. A reliable way to use [HttpClient](httpclient.md) with an XML parser is to call the [GetBufferAsync](httpclient_getbufferasync.md) method and parse the buffer for the "&lt;?xml&gt;" element. Then use the character encoding specified ("&lt;xmlversion="1.0" encoding="UTF-8"?&gt;", for example) to parse the HTTP response body. For other text formats, similar methods can be used where the app scans the initial part of the HTTP response body to determine the character encoding used.

### Exception Handling

You must write code to handle exceptions when you call this method. Exceptions can result from parameter validation errors, name resolutions failures, and network errors. Exceptions from network errors (loss of connectivity, connection failures, and HTTP server failures, for example) can happen at any time. These errors result in exceptions being thrown. If not handled by your app, an exception can cause your entire app to be terminated by the runtime. For more information on how to handle exceptions, see [Handling exceptions in network apps](http://msdn.microsoft.com/library/76fafcc9-c674-4cf8-baa0-2400638fae35).

## -examples

## -see-also
[IAsyncOperationWithProgress(String, HttpProgress)](../windows.foundation/iasyncoperationwithprogress_2.md), [Uri](../windows.foundation/uri.md)