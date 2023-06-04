
- Some function names have been changed to work with Nautilus.
  - `htonl` is now `lwip_htonl`
  - `getpeername` is now `lwip_getpeername`
  - `inet_ntoa` is now `ip4addr_ntoa`
  - `close` is now `lwip_close`
  - `setsockopt` is now `lwip_setsockopt`
- No messages will be printed to `stderr`.
- The call to `gethostname` is removed and the hostname is "host" now.
- `rfbScreenInfoPtr::deferUpdateTime` must be 0, since `gettimeofday` function calls will not work and non-zero values will require that.
