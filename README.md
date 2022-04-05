# ansible-modify-file

```bash
- 
  name: Replace Line
  hosts: ubuntu
  vars:
    amf_value: 192.168.5.95
  tasks:
    - name: Update AMF config
      replace:
        path: /home/ubuntu/amf.yml
        after: 'ngap:'
        before: 'guami'
        # regexp: '^(\s*enable = )false$'
        regexp: '(\-\s+addr\:\s)+127\.0\.0\.5'
        # replace: '\g<1>true'
        replace: '\g<1>{{ amf_value }}'
        backup: yes
```
