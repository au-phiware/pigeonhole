# pigeonhole

Send and receive GPG encrypted documents to and from a redis database with Bash!

# Usage

    pigeonhole put recipient

Encrypt the standard input with the first public key found in your GPG keyring
that matches `recipient`, also signs the result with the first secret key found
in your GPG keyring. Store the result in a Redis database using the public key's
ID as the key.

    pigeonhole get

Retrieves and decrypts a document stored in a Redis database, using the first
secret key's ID found in your GPG keyring for the key and places the result on
the stadard output.

    pigeonhole length [recipient]

Retrieves the number of available documents for recipient (or yourself).
