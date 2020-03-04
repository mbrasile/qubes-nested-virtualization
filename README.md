# h1 qubes-nested-virtualization
Nested virtualization in Qubes OS

According the Qubes OS developers' team, Xen (preview) nested virtualization is not their priority because their focus is on security and stability of the operative system ( https://github.com/QubesOS/qubes-issues/issues/4104#issuecomment-406080934 ).

Anyway, if you need to develop Android Apps and you love to work with Qubes, you are probably stuck with the limitation that Google added on AVD since Android 8 that need Vt-x / Vt-d flags on to work.

Luckily, since Qubes is open-source, it is possible to compile the Xen modules enabling the preview options.

in  /usr/share/qubes/templates/libvirt/xen.xml ( https://github.com/QubesOS/qubes-core-admin/blob/master/templates/libvirt/xen.xml ) just change

```html
<feature name='vmx' policy='disable'/>
<feature name='svm' policy='disable'/>
```

to

```html
<feature name='vmx' policy='enable'/>
<feature name='svm' policy='enable'/>
```

( ref. https://dev.qubes-os.org/projects/core-admin/en/latest/libvirt.html )
