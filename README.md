# ![LOGO](logo.png) DataLakeStoreFileSystemManagementClient **flow**ground Connector

## Description

A generated **flow**ground connector for the DataLakeStoreFileSystemManagementClient API (version 2016-11-01).

Generated from: https://api.apis.guru/v2/specs/azure.com/datalake-store-filesystem/2016-11-01/swagger.json<br/>
Generated at: 2019-05-07T17:37:59+03:00

## API Description

Creates an Azure Data Lake Store filesystem client.

## Authorization

This API does not require authorization.

## Actions

### Appends to the specified file, optionally first creating the file if it does not yet exist. This method supports multiple concurrent appends to the file. NOTE: The target must not contain data added by Create or normal (serial) Append. ConcurrentAppend and Append cannot be used interchangeably; once a target file has been modified using either of these append options, the other append option cannot be used on the target file. ConcurrentAppend does not guarantee order and can result in duplicated data landing in the target file.

*Tags:* `FileSystem`

#### Input Parameters
* `path` - _required_ - The Data Lake Store path (starting with '/') of the file to which to append using concurrent append.
* `appendMode` - _optional_ - Indicates the concurrent append call should create the file if it doesn't exist or just open the existing file for append
    Possible values: autocreate.
* `op` - _required_ - The constant value for the operation.
    Possible values: CONCURRENTAPPEND.
* `Transfer-Encoding` - _required_ - Indicates the data being sent to the server is being streamed in chunks.
    Possible values: chunked.
* `syncFlag` - _optional_ - Optionally indicates what to do after completion of the concurrent append. DATA indicates that more data will be sent immediately by the client, the file handle should remain open/locked, and file metadata (including file length, last modified time) should NOT get updated. METADATA indicates that more data will be sent immediately by the client, the file handle should remain open/locked, and file metadata should get updated. CLOSE indicates that the client is done sending data, the file handle should be closed/unlocked, and file metadata should get updated.
    Possible values: DATA, METADATA, CLOSE.
* `api-version` - _required_ - Client Api Version.

### Sets or removes the expiration time on the specified file. This operation can only be executed against files. Folders are not supported.

*Tags:* `FileSystem`

#### Input Parameters
* `path` - _required_ - The Data Lake Store path (starting with '/') of the file on which to set or remove the expiration time.
* `expiryOption` - _required_ - Indicates the type of expiration to use for the file: 1. NeverExpire: ExpireTime is ignored. 2. RelativeToNow: ExpireTime is an integer in milliseconds representing the expiration date relative to when file expiration is updated. 3. RelativeToCreationDate: ExpireTime is an integer in milliseconds representing the expiration date relative to file creation. 4. Absolute: ExpireTime is an integer in milliseconds, as a Unix timestamp relative to 1/1/1970 00:00:00.
    Possible values: NeverExpire, RelativeToNow, RelativeToCreationDate, Absolute.
* `expireTime` - _optional_ - The time that the file will expire, corresponding to the ExpiryOption that was set.
* `op` - _required_ - The constant value for the operation.
    Possible values: SETEXPIRY.
* `api-version` - _required_ - Client Api Version.

### Checks if the specified access is available at the given path.

*Tags:* `FileSystem`

#### Input Parameters
* `path` - _required_ - The Data Lake Store path (starting with '/') of the file or directory for which to check access.
* `fsaction` - _required_ - File system operation read/write/execute in string form, matching regex pattern '[rwx-]{3}'
* `op` - _required_ - The constant value for the operation.
    Possible values: CHECKACCESS.
* `api-version` - _required_ - Client Api Version.

## License

**flow**ground :- Telekom iPaaS / azure-com-datalake-store-filesystem-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
