# Ansible Playbook: inventory2librenms

[![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=popout-square)](licence) 

## Description

Ansible Playbook that writes the whole invenotry into Librenms.

## Playbook Variables

| Variable             | Default     | Comments (type)                                   |
| :---                 | :---        | :---                                              |
| inventory2librenms_url |  | URL of your Librenms instance |
| inventory2librenms_token | | API Key of your Librenms instance |
| inventory2librenms_body | | Contents of the post body see [examples](#Example) for snmp versions.|

### Example

#### SNMP v1

```yml
inventory2librenms_body:
  hostname: "{{ item }}"
  version: "v1"
  community: "public"
```

#### SNMP v2
```yml
inventory2librenms_body:
  hostname: "{{ item }}"
  version: "v2"
  community: "public"
```

#### SNMP v3

```yml
inventory2librenms_body:
  authlevel: authPriv
  authname: "{{ snmp_user }}"
  authpass: "{{ snmp_password }}"
  authalgo: "SHA"
  cryptopass: "{{ snmp_encryption }}"
  cryptoalgo: "DES"
  hostname: "{{ item }}"
  version: "v3"
```

### 1.1.0

* fix hostname is lower

### 1.0.0

* inital role

## Author

* [Simon Bärlocher](https://sbaerlocher.ch)
* [ITIGO AG](https://www.itigo.ch)

## License

This project is under the MIT License. See the [LICENSE](licence) file for the full license text.

## Copyright

(c) 2018, Simon Bärlocher
(c) 2018, ITIGO AG