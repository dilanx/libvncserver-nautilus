# libvncserver-nautilus

## Updates

- `htonl` is now `lwip_htonl`
- `getpeername` is now `lwip_getpeername`
- `inet_ntoa` is now `ip4addr_ntoa`
- `close` is now `lwip_close`
- `setsockopt` is now `lwip_setsockopt`
- `select` is now `lwip_select`
- `recvfrom` is now `lwip_recvfrom`
- `connect` is now `lwip_connect`
- `accept` is now `lwip_accept`
- `recv` is now `lwip_recv`
- `htons` is now `lwip_htons`
- `socket` is now `lwip_socket`
- `inet_addr` is now `ipaddr_addr`
- `gethostbyname` is now `lwip_gethostbyname`
- `bind` is now `lwip_bind`
- `listen` is now `lwip_listen`
- `fcntl` is now `lwip_fcntl`
- `getsockopt` is now `lwip_getsockopt`
- `malloc` is now `kmem_malloc`
- `free` is now `kmem_free`

## Removals

- `stdio.h` and `stdlib.h` includes are removed.
- No messages will be printed to `stderr`.
- The call to `gethostname` is removed and the hostname is "host" now.
- `rfbScreenInfoPtr::deferUpdateTime` must be 0, since `gettimeofday` function calls will not work and non-zero values will require that.
- Removed calls to `sscanf`, which is referrencing `__isoc99_sscanf`. Hopefully it doesn't matter too much for now.
- Removed call to `rfbProcessFileTransfer` in the `rfbProcessClientNormalMessage` function.
- `sraSpanListPrint` now does nothing.
- The calls to `rfbSendFileTransferChunk` are now removed.
- Removed chunk with call to `getrlimit`.
- `rfbEncryptAndStorePasswd` and `rfbRandomBytes` now does nothing. This shouldn't matter too much since we're not really using auth.
- `rfbUsage` now does nothing. Hopefully this shouldn't matter too much since we're not using the CLI.
