# cURL-OpenSSL-update
To use  CURLOPT_SSLVERSION 6 / TSLv 1.2 (i. e. PayPal API)

-----------------------------------------------------------------------------------------

/* Before updating cURL try to connect to PayPal */
$ curl -v https://api.sandbox.paypal.com

/* If results i. e. "curl: (35) error:14077410:SSL routines:SSL23_GET_SERVER_HELLO:sslv3 alert handshake failure" 
you are not able to use CURLOPT_SSLVERSION => 6! */

/* These commands were performed on ubuntu 12.04 to fix this problem and update cURL/OpenSSL
$ apt-get install python-software-properties
$ add-apt-repository ppa:rsrchboy/ppa
$ apt-get update
$ apt-get --only-upgrade install curl openssl libssl1.0.0 libssl-dev

/* Should be successful now */
$ curl -v https://api.sandbox.paypal.com

/* Now you should be able to use TSLv 1.2 */
CURLOPT_SSLVERSION => 6
