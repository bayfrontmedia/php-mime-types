## PHP MIME types

Simple class used to detect appropriate MIME type.

This is by no means meant to handle an exhaustive list of every single MIME type, but rather focuses on the [most common MIME types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types) used.

Since MIME types will be detected using the file extension, some file extension related methods are available to use as well.

- [License](#license)
- [Author](#author)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)

## License

This project is open source and available under the [MIT License](LICENSE).

## Author

<img src="https://cdn1.onbayfront.com/bfm/brand/bfm-logo.svg" alt="Bayfront Media" width="250" />

- [Bayfront Media homepage](https://www.bayfrontmedia.com?utm_source=github&amp;utm_medium=direct)
- [Bayfront Media GitHub](https://github.com/bayfrontmedia)

## Requirements

* PHP `^8.0` (Tested up to `8.4`)

## Installation

```
composer require bayfrontmedia/php-mime-types
```

## Usage

- [getMimeTypes](#getmimetypes)
- [addMimeType](#addmimetype)
- [getExtension](#getextension)
- [hasExtension](#hasextension)
- [fromExtension](#fromextension)
- [fromFile](#fromfile)

<hr />

### getMimeTypes

**Description:**

Return array of all MIME types.

**Parameters:**

- None

**Returns:**

- (array)

**Example:**

```
use Bayfront\MimeTypes\MimeType;

print_r(MimeType::getMimeTypes());
```

<hr />

### addMimeType

**Description:**

Adds new MIME type definitions.

**Parameters:**

- `$types` (array): Array whose keys are the file extension and values are the MIME type string

**Returns:**

- (void)

**Example:**

```
use Bayfront\MimeTypes\MimeType;

MimeType::addMimeType([
    'acgi' => 'text/html',
    'avs' => 'video/avs-video'
]);
```

<hr />

### getExtension

**Description:**

Return extension of a given file, or empty string if not existing.

**Parameters:**

- `$file` (string)

**Returns:**

- (string)

**Example:**

```
use Bayfront\MimeTypes\MimeType;

echo MimeType::getExtension('pretty-photo.jpg');
```

<hr />

### hasExtension

**Description:**

Checks if a file has a given extension.

**Parameters:**

- `$extension` (string)
- `$file` (string)

#### Returns:

- (bool)

**Example:**

```
use Bayfront\MimeTypes\MimeType;

if (MimeType::hasExtension('jpg', 'pretty-photo.jpg') {
    // Do something
}
```

<hr />

### fromExtension

**Description:**

Get MIME type from file extension.

**Parameters:**

- `$extension` (string)
- `$default = 'application/octet-stream'` (string): Default MIME type to return if none found for given extension

**Returns:**

- (string)

**Example:**

```
use Bayfront\MimeTypes\MimeType;

echo MimeType::fromExtension('jpg');
```

<hr />

### fromFile

**Description:**

Get MIME type from file name.

**Parameters:**

- `$file` (string)
- `$default = 'application/octet-stream'` (string): Default MIME type to return if none found for given extension

**Returns:**

- (string)

**Example:**

```
use Bayfront\MimeTypes\MimeType;

echo MimeType::fromFile('pretty-photo.jpg');
```