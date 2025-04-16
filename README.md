How can i contact you?

# nr7302
notes on accessing a zyxel nr7302 from telenor



## initial state:
- No accessible ports by default.
- Serial console is available through headers.
- password generators does not produce correct result

## gaining access:
- iptables -F Service_HTTPS
- root user active but no web permissions
- supervisor/admin user disabled
- backup/restore or modification of zcfg_config.json is overwritten on reload
- Other attempts:
  - zycli mgmtsrvctl config --service HTTPS 4 --port 443 --trustdomain --trustdomain  add 192.168.2.0/24 
  - cat /usrdata/factory_reset 
  - zycli fwidcheck off
  - zycli modelcheck off		   
  - zycli sys  atwz
  - zycli sys atcr

##firmware link
- http://fw-acs.telekom.de/tftpboot/BDTX5GNR7302WZ/100ACHA4b5_F0.bin
  - no web access
  - zycast does not support reset to factory
  - zycli does not support reset to factory?

## next
- erase factory partition?
- activate supervisor/admin user?
- 
