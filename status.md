## News

new: libioth: The definitive API for the Internet of Threads

* the API is minimal: Berkeley Sockets + msocket + newstack/delstack.
* the stack implementation can be chosen as a plugin at run time.
* netlink based stack/interface/ip configuration via _nlinline_.
* ioth sockets are real file descriptors, poll/select/ppoll/pselect/epoll friendly
* plug-ins are loaded in private address namespaces: libioth supports several stacks
of the same type (same plugin) even if the stack implementation library was designed to
provide just one stack.

---

new: vdeplug4, libpam-net ad umps3 are now in SID

As a consequence of vdeplug4, user-mode linux and virtualbox available in SID
can now use the rich set of new vde plugins out of the box... pardon, out of the package.
(qemu/kvm was already compatible).

---

new: vde-2 new packet is in Debian SID.

----

new: [picotcp](https://github.com/virtualsquare/picotcp): picoTCP is a small-footprint, 
modular TCP/IP stack designed for embedded systems and the Internet of Things. 
There is also an exprerimental-still unofficial Debian package (on 
[salsa](https://salsa.debian.org/virtualsquare-team/picotcp)) which
generates/installs a shared library to support IoTh (Internet of Threads).

Warning: picotcp is *not* yet ready to enter Debian. We are working on it.

----

New: [vufusearchive](https://github.com/virtualsquare/vufusearchive)
A `vufuse module based on libarchive: it supports tar/zip/iso (including compressed archives)

----

New: [fusefatfs/vufusefatfs](https://github.com/virtualsquare/fusefatfs): 
FUSE/VUOS-vufuse module for FAT12/16/32 and exFAT.

----

New: The pages of the tutorials are almost complete. Give it a try, it is the 
third menu here above!

----

New vde\_plug: `vdesl`.

This vde\_plug creates a virtual point to point ethernet link over a serial line.

Example: connect the uart ports of two Raspberry PI boards (GND-\>GND, TXD-\>RXD, RXD-\>TXD).

The following command (on both RasPIs):
```bash
       sudo vde_plug -d tap://vdesl0 vdesl:///dev/ttyAMA0[speed=4000000]
```

creates a 4Mbps ethernet link connecting the two `vdesl0` interfaces.


## Debian

Warning: debhelper compat 5 and 6 are now planned for removal. V² packages affected:
fuse-umfuse-ext2, vdetelweb.

### TODO:
  * fuse-umfuse-ext2, vdetelweb: update debhelper (ready for uploading)
  * purelibc: FTBFS still pending a FTBFS error for riscv64
  * libvpoll-eventfd on salsa is ready to be submitted in new for SID
  * vdeplug_slirp has been packaged on Salsa. It should be ready to be uploaded to SID
  *	vdeplug_vdels, vdeplug_vlan, vdeplug_agno, vdeplug_pcap: should be ready to be uploaded to SID
  * libexecs: The package on salsa is ready for SID (convert from autotools to cmake + migrate to the virtualsquare team)

  *	vuos: fix module/submodule install path to support multi arch. To be packaged
  * fusefatfs: to be packaged (after vuos?)
  * vufusearchive: to be packaged (after vuos).
  * libnlq: docs/man missing, to be packaged

  * nsutils? change cmdline syntax? convert from autotools to cmake. Is this meaningful in Debian? compare with lsns

### packaged projects 
#### Debian SID/testing
  * vdeplug4
  * cado
  * vdens
  * libvdeplirp
  * libvdestack
  * strcase
  * userbindmount
  * libvolatilestream
  * libfduserdata
  * libstropt
  * nlinline
  * randmac
  * libpam-net
  * umps3

#### in Debian stable
  * libexecs (move to virtualsquare team)

### purelibc
purelibc 1.0.3 is in sid and testing. Some work must be done to port on some architectures.
NEW: faccessat emulation added. NEW: the compatibility problems for x32 should have been fixed.

### vdeplug\_slirp, vdeplug\_vdesl, vdeplug\_vlan
Ready to be packaged.

Note: can enter experimental only as it needs vdeplug4

### libvpoll-eventfd
Packaged. Some checks needed for the kernel module. Almost ready for the NEW queue.

## Open Suse
[... add status here]

## Arch
[... add status here]

## Not yet ready for packaging:

### libnlq
doc is still missing

### vuos
freeze a stable relase for packaging.

### vxvdex
still too experimental

### nsutils
could be packaged, it is a useful tool.

## Bleeding edge of developing

### fuse modules

### lwip new

### picox

### dnsutils

### mutli-arch support for vuos modules

## Design stage

### new vde\_switch

### new vde\_wirefilter

### new vdetelweb

### lwip/lwipv6 convergence
