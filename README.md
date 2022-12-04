<h1 align="center">
  CryptoPie
</h1>
<h4 align="center">
  Encryptor, decryptor, encoder and decoder with implemented collection of cryptography and encoding algorithms and CLI interface
</h4>
<p align="center">
  <a href="https://github.com/rostok2112/CryptoPie/blob/main/LICENSE"><img alt="GitHub license" src="https://img.shields.io/github/license/rostok2112/CryptoPie.svg">
  </a>
</p>
## Requirements

- Python3
- Optionally:
  - PipEnv

## Dependencies installation

If you have pipenv you can install or update dependencies by:

```bash
pipenv sync
```

Else:

```bash
pip install -r requirements.txt
```

Install new dependencies  if you have pipenv:

```bash
pipenv install <name_of_package>
pipenv requirements > requirements.txt
```

Else:

```bash
pip install <name_of_package>
pip freeze > requirements.txt
```

## Usage

```text
usage: python crypto_pie.py [-h] {encrypt,decrypt} [-p [PATHES ...]] [-d DESTINATION] [-r] [-k KEY] [-b [BORDERS ...]]
                         [-e {utf-8, ascii, ...}]
                         {ceasar,replacement,additive_stream,s-des-block,rsa} ... input [input ...]

Encryptor/Decryptor/Encoder/Decoder with CLI interface

positional arguments:
  {encrypt,decrypt,generate_key,encode,decode}     List of purposes handlers
    encrypt             Encrypt options
      options:
        -h, --help            show help message
        -p [PATHES ...], --pathes [PATHES ...]
                              A path/pathes to a file/files/directory/directories
        -d DESTINATION, --destination DESTINATION, --dest DESTINATION
                              Destination path
        -r, --recursively     Recursively encrypt/decrypt everuthing in input path. Doesnt do anything if file on input
        -v, --verbose         Print results into stdout
        -k KEY, --key KEY     The value by which an input will be encrypted/decrypted
        -g, --generate_key  Generate random key
        -b [BORDERS ...], --borders [BORDERS ...]
                              Alphabet/alphabets borders in format: a-z A-Z а-я А-Я
        -e {utf-8, ascii, ...}, --encoding {utf-8, ascii, ...}
                              Encoding of texts of input and output files
    decrypt             Decrypt options
      options:
        -h, --help            show help message
        -p [PATHES ...], --pathes [PATHES ...]
                              A path/pathes to a file/files/directory/directories
        -d DESTINATION, --destination DESTINATION, --dest DESTINATION
                              Destination path
        -r, --recursively     Recursively encrypt/decrypt everuthing in input path. Doesnt do anything if file on input
        -v, --verbose         Print results into stdout
        -k KEY, --key KEY     The value by which an input will be encrypted/decrypted
        -b [BORDERS ...], --borders [BORDERS ...]
                              Alphabet/alphabets borders in format: a-z A-Z а-я А-Я
        -e {utf-8, ascii, ...}, --encoding {utf-8, ascii, ...}
                              Encoding of texts of input and output files
    generate_key             Decrypt options
      options:
        -h, --help            show help message
        -l LENGTH_KEY, --length_key LENGTH_KEY     
                              Specify length of random key
        -b [BORDERS ...], --borders [BORDERS ...]
                              Alphabet/alphabets borders in format: a-z A-Z а-я А-Я
    encode
    decode
  {ceasar,substitution,additive_stream,s-des-bloc,rsa}   A cryptographic algorithm for encryption/decryption
    ceasar 
      key format:
        integer_num,  -inf <= integer_num <= inf
        May be any positive or negative integer
    substitution
      key format:
        value_to_be_replaced1:value_to_replace1,value_to_be_replaced2:value_to_replace1,...
        Sequence of pairs of values to be replace and values to replace and values to be replaced by this value
    additive_stream
      options:
        -l LENGTH_KEY, --length_key LENGTH_KEY     
                              Specify length of random key
      key format:
        interval_to_encrypt1:interval1_key1,interval1_key2,interval1_key3,...;interval_to_encrypt2:interval2_key1,interval2_key2,interval2_key3,...;... interval_to_encrypt1 - in format a-z, A-Z; 0 <=interval_key <= length of interval
        Sequence of pairs of intervals to encrypt and sequence of keys for encryption. The length of keys sequence must be greater than 3 or equal to count + 1 of characters if count is lesser than 3. It is best if the length of the keys sequence is equal to the count of characters of the input text
    s-des-block
    rsa
  {b64,}   An encoding/decoding algorithm 
options:
        -h, --help            show help message
```

Use by:

```bash
cd src/
python crypto_pie.py [purpose] [method] [options] <input>
```

Or if pipenv installed:

```bash
pipenv run crypto_pie [purpose] [method] [options] <input>
```
