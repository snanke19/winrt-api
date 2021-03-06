---
-api-id: M:Windows.Services.Store.StoreAvailability.RequestPurchaseAsync(Windows.Services.Store.StorePurchaseProperties)
-api-type: winrt method
---

<!-- Method syntax
public Windows.Foundation.IAsyncOperation<Windows.Services.Store.StorePurchaseResult> RequestPurchaseAsync(Windows.Services.Store.StorePurchaseProperties storePurchaseProperties)
-->

# Windows.Services.Store.StoreAvailability.RequestPurchaseAsync

## -description
Requests the purchase of the current SKU availability and displays the UI that is used to complete the transaction via the Windows Store. This method provides the option to specify additional details for a specific offer within a large catalog of products that are represented by a single listing in the Windows Store, including the product name to display to the user during the purchase.

> [!IMPORTANT]
> This method must be called on the UI thread.

## -parameters
### -param storePurchaseProperties
An object that specifies additional info for the purchase request, including the product name to display to the user during the purchase.

## -returns
An asynchronous operation that, on successful completion, returns a [StorePurchaseResult](storepurchaseresult.md) object that provides status and error info about the purchase.

## -remarks
If this method is not called on the UI thread, the [StorePurchaseResult](storepurchaseresult.md) return value might indicate that an error occurred, and the [ExtendedError](storepurchaseresult_extendederror.md) property could have the value 0x800706be. This value corresponds to the [RPC_S_CALL_FAILED](https://msdn.microsoft.com/en-us/library/windows/desktop/aa378645(v=vs.85).aspx) error code.

## -examples

## -see-also
[RequestPurchaseAsync](storeavailability_requestpurchaseasync_1696674465.md)