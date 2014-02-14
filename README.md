# LDAPAuthenticate

LDAPAuthenticate is a CakePHP 2.0 Plugin, that make your authenticate with ldap very simple!

## Requirements

PHP 5.3 or >
CakePHP 2.0 or >

## Installation

Clone from github : in your app directory type git clone git@github.com:pmoraes/LDAPAuthenticate.git

## Usage

You need to configure the plugin in your appController below follow how to configure

```php
'Auth' => array(
      'authenticate' => array(
        'LDAPAuthenticate.LDAP' => array(
                'ldap_protocol'=> // This parameter is optional, default is 3, but if you need other configuration you change
                'ldap_url'     => 'example.domain.com',

                // Configure your UID or CN and your Domain Component 
                'ldap_bind_dn' => 'uid=??,ou=users,dc=??,dc=??',
                'ldap_bind_pw' => 'atomic10',
                'model'        => 'User',

                // Configure your Domain Component
                'ldap_base_dn' => 'dc=??,dc=??', 

                'ldap_filter'  => '(|(UID=%USERNAME%*)(uid=%USERNAME%*))',

                // Configure this fields how to are in your form 
                'form_fields'  => array('username' => '??', 'password' => '??'),

                // This fields are references to database table
                'ldap_to_user' => array(
                  'givenname'  => 'first_name',
                  'sn'         => 'last_name',
                  'mail'       => 'mail',
                  'uid'        => 'username'
              ),
              'defaults'       => array(
              'active'    => 1,
              'admin'     => 0
          )
        )
      )
    )