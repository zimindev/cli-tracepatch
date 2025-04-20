# 🛣️ tracepath — Lightweight Network Path Tracer

**tracepath** is a simple CLI tool for tracing the route packets take to a network host. Unlike `traceroute`, it doesn’t require superuser privileges and provides a clean overview of each hop and path MTU (Maximum Transmission Unit).

---

## ✅ Features

- Does not require root privileges
- Automatically determines path MTU
- Provides hop-by-hop latency information
- Lightweight and available by default on many systems

---

## 🔧 Installation

### Debian/Ubuntu
```bash
sudo apt install iputils-tracepath
```

### Arch Linux
```bash
sudo pacman -S iputils
```

### Fedora
```bash
sudo dnf install iputils
```

---

## 🚀 Basic Usage

### Trace the route to a domain or IP
```bash
tracepath example.com
```

### Specify the network interface
```bash
tracepath -i eth0 example.com
```

### Limit the number of hops
```bash
tracepath -m 15 example.com
```

---

## 📊 Output Example

```txt
 1?: [LOCALHOST]                                         pmtu 1500
 1:  192.168.1.1                                          0.123ms 
 2:  10.0.0.1                                             2.104ms 
 3:  no reply
 4:  93.184.216.34                                        25.325ms reached
     Resume: pmtu 1500 hops 4 back 63
```

- `pmtu` — maximum transmission unit size along the path
- Each hop shows IP and round-trip latency
- `no reply` means the hop didn’t respond
- `reached` indicates the destination was reached

---

## 🧩 Tips

- Great tool for quick diagnostics without needing `sudo`
- Works well in scripts or quick network checks
- If `tracepath` is unavailable, `mtr` and `traceroute` are good alternatives

---

## 📚 More Info

- Run `man tracepath` for full documentation
- Reference: [https://man7.org/linux/man-pages/man8/tracepath.8.html](https://man7.org/linux/man-pages/man8/tracepath.8.html)
