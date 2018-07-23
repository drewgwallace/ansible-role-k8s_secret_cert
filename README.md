# Ansible Role

## Purpose
  Add cert to Kubernetes secrets.

----

## Execution

<pre>
    - hosts: all
      tasks:
      - include_role:
          name: drewgwallace.k8s_secret_cert
        vars:
          container_name: <b>"MY_CONTAINER"</b>
</pre>

  ### Variables:
<pre>
    container_name: Name of container, the other variables have defaults based on this requirement.
    path_to_cert: Defaults to /tmp/<b>{{ container_name }}</b>.crt , path to a x509 certificate.
    path_to_raw_key: Defaults to /tmp/<b>{{ container_name }}</b>_priv.key , path to a unencrypted private key used to generate certificate.
    create_secrets: Optionally set to false to skip execution of creating the secret in k8s cluster.
    openssl_force_regeneration: Defaults to <b>false</b>, set to true to override existing object.
</pre>
----

## Notes

+ Look at drewgwallace.ansible-role-open_ssl_self_signed to create self signed certificates for use in generating secrets.
