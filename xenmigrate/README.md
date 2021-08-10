# xenmigrate.py

This file is used to convert between XenServer .xva files and opensource Xen .img files. The old script (graciously by Jolokia Networks)
and provided by https://github.com/hswayne77 seems out of date and does not run. Instead, when used from the prompt a an error will
be displayed:

"UnboundLocalError: local variable 'source' referenced before assignment"

Script was slightly modified by me to fix this.


# Quick user guide 

```
# 解壓縮xva 
tar -xf xva-name.xva 

# 查看有哪些Ref開頭的資料夾 
ls Ref* 

# 轉換成raw image 
python xenmigrate.py -c Ref:123 vm_raw_0.img 

# 需要的話再轉成qcow2 
qemu-img convert -f raw -O qcow2 vm_raw_0.img vm_0.qcow2
```

