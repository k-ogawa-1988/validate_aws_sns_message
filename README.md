# validate_aws_sns_message

Validate integrity of Amazon SNS messages.

Refined from `validatesns`.

* Verifies cryptographic signature.
* Checks signing certificate is hosted on an Amazon-controlled URL.
* Requires message be no older than one hour, the maximum lifetime of an SNS message.

Licence: [MIT](https://opensource.org/licenses/MIT)

## Quick start

```shell

pip install validate_aws_sns_message

```

```python

import validate_aws_sns_message

# Raise validate_aws_sns_message.ValidationError if message is invalid.
validate_aws_sns_message.validate(decoded_json_message_from_sns)

```

## Gotchas

The ``validate`` function downloads the signing certificate on every call. For performance reasons, it's worth caching certificates - you can do this by passing in a ``get_certificate`` function.

This takes a ``url``, and returns the certificate content. Your function could cache to the filesystem, a database, or wherever makes sense.

## Contribute

Github: <https://github.com/kenichi-ogawa-1988/validate_aws_sns_message>

## Special thanks

* Original `validatesns`: <https://github.com/nathforge/validatesns>
