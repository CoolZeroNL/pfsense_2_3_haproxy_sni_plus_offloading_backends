## Frontends on 1 IP serving websites from several backends

Features used: acl's / actions / offloading / SNI / certificates

- Some HTTPS traffic is forwarded as-is to the backend while using SNI to select differentiate between different domains
- Some HTTPS traffic is decrypted on haproxy, then host header is used for selecting the backend
- For some domains HTTP traffic is redirected to HTTPS, others are served by the default backend.

If SNI backend selection without offloading is not required for some, then Frontend2 does not need to be configured, and Frontend3 should be configured to listen on WAN:443

### Frontend / Backend overview
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/Frontends.png)
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/Backends.png)

### Frontend 1
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/FE1.png)
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/FE1-acls.png)

### Frontend 2
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/FE2.png)
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/FE2-acls.png)

### Frontend 3
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/FE3.png)
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/FE3-settings.png)
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/FE3-certificate.png)

### Backends
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/backend-forum.png)
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/backend-portal.png)
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/backend-support.png)
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/backend-www.png)

### offloading backend with special check
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/backend-offloading.png)
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/backend-offloading-check.png)

### Stats
![](https://raw.githubusercontent.com/wiki/PiBa-NL/pfsense-haproxy-package-doc/pfsense_2_3_haproxy_sni_plus_offloading_backends/Stats.png)
