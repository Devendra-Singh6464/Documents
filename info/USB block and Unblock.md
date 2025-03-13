    - name: Block USB access
      shell: chmod 700 /media && /bin/sed -i '/GRUB_DISABLE_RECOVERY="true"/s/^#//g' /etc/default/grub


*Unblock USB*
``` d
sudo chmod 777 /media/
```

*Block USB*
``` d
sudo chmod 700 /media/
```
