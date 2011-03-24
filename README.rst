=======
PHP SoapClient with SOAP Message Security
=======


Requirements
------------

- PHP compiled with SOAP support
- xmllint_ utility (ubuntu/debian has it in libxml2-utils package)
- 

.. _xmllint: http://xmlsoft.org/xmllint.html


Usage 
-----

You should set certificate (in PFX or PKCS7 format) while initializng class. Other
HTTP options, identical to HTTPRequest_ class request options are accepted too::

        $client = new SignedSoapClient(
                'https://example.com?wsdl', 
                array(
                        'ssl' => array(
                                'cert' => '/file',
                                'certpasswd' => 'password'
                                )
                        )
        );

.. _HTTPRequest: http://php.net/HTTPRequest

Class signes SOAP-ENV:Body part of the message by default, this behaviour can be changed
in ``buildSignedInfo`` method.