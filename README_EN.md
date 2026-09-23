# v2ray-termux

A lightweight and simple **Xray/V2Ray client for Termux on Android**, designed to run an Xray-based proxy directly from your phone and provide a local SOCKS5 endpoint for other applications.

The project is focused on keeping the setup simple while making it possible to use Xray networking capabilities directly from a Termux environment.

---

## ✨ Features

- 📱 Designed for Android + Termux
- ⚡ Lightweight and terminal-based
- 🔐 VLESS + Reality support
- 🌐 Local SOCKS5 proxy
- 🔌 Default local proxy: `127.0.0.1:1080`
- 📲 Can be used by SOCKS5-compatible applications
- 🛠️ Simple installation and startup scripts
- 📦 Includes Xray binaries
- 🧩 Configurable Xray configuration
- 💻 Supports both `xray` and `xray32` binaries

---

## 📋 Requirements

Before installing, make sure you have:

- An Android device
- Termux
- Internet access
- A valid Xray/VLESS configuration

> The project is intended to be used inside a Termux environment.

---

## 🚀 Installation

### 1. Update Termux

```bash
pkg update && pkg upgrade -y
```

### 2. Install Git

```bash
pkg install git -y
```

### 3. Clone the repository

```bash
git clone https://github.com/sepantartd/v2ray-termux.git
```

### 4. Enter the project

```bash
cd v2ray-termux
```

### 5. Run the installer

```bash
bash install.sh
```

---

## ▶️ Start Xray

Start the client with:

```bash
bash start.sh
```

The Xray client will start using the project's configuration.

By default, the local SOCKS5 endpoint is:

```text
127.0.0.1:1080
```

Keep Termux running while the proxy is in use.

---

## ⚙️ Configuration

The main Xray configuration can be found in:

```text
xray/config.json
```

Edit the configuration according to your own server and connection details.

For example:

```bash
nano xray/config.json
```

After changing the configuration, restart Xray:

```bash
bash start.sh
```

---

## 🌐 SOCKS5 Proxy

Once Xray is running, applications that support SOCKS5 can connect through:

```text
Host: 127.0.0.1
Port: 1080
Protocol: SOCKS5
```

This allows applications on the Android device to use the local Xray proxy.

---

## 📱 Telegram

Telegram can use the local SOCKS5 proxy.

Go to:

```text
Telegram
→ Settings
→ Data and Storage
→ Proxy
→ Add Proxy
```

Select:

```text
SOCKS5
```

Then enter:

```text
Server: 127.0.0.1
Port: 1080
```

Save and enable the proxy.

Make sure Xray is already running in Termux.

---

## 📲 v2rayNG

The local SOCKS5 listener can also be used by applications such as v2rayNG when configured to accept a SOCKS5 endpoint.

Use:

```text
Address: 127.0.0.1
Port: 1080
```

Start Xray first:

```bash
bash start.sh
```

Then configure the application to use the local SOCKS5 proxy.

---

## 🛑 Stop Xray

To stop the running process:

```text
Ctrl + C
```

Closing the Termux session can also terminate the running Xray process.

---

## 🔄 Restart

To start the client again:

```bash
cd v2ray-termux
bash start.sh
```

---

## 📁 Project Structure

```text
v2ray-termux/
├── xray/
│   └── config.json
├── xray32/
├── configs.txt
├── install.sh
├── start.sh
├── LICENSE
└── README.md
```

The exact contents may change as the project evolves.

---

## 🧰 Scripts

### `install.sh`

The installation script prepares the Termux environment and project for use.

Run:

```bash
bash install.sh
```

### `start.sh`

Starts the Xray client using the configured settings.

Run:

```bash
bash start.sh
```

---

## 🔧 Troubleshooting

### Xray does not start

Make sure you are inside the project directory:

```bash
cd v2ray-termux
```

Then try:

```bash
bash start.sh
```

Check that your configuration is valid.

---

### Telegram cannot connect

Verify that:

```text
SOCKS5
127.0.0.1
1080
```

is configured in Telegram.

Also make sure Xray is currently running in Termux.

---

### v2rayNG cannot connect

Check that:

1. Xray is running.
2. The local address is `127.0.0.1`.
3. The local port is `1080`.
4. The Xray configuration is valid.

---

### The connection does not work

A working local SOCKS5 listener does not necessarily mean that the remote Xray configuration is valid.

Check:

- Server address
- Server port
- UUID
- VLESS settings
- Reality public key
- Reality short ID
- SNI/server name
- Network configuration
- DNS configuration

---

## 🔐 Security

Never publish sensitive credentials or private keys in a public repository.

Avoid committing:

```text
Private keys
Authentication credentials
Personal server credentials
Sensitive configuration data
```

If you publish an example configuration, remove private information first.

---

## 📦 Updating

To get the latest version of the repository:

```bash
cd ..
rm -rf v2ray-termux
git clone https://github.com/sepantartd/v2ray-termux.git
cd v2ray-termux
bash install.sh
```

---

## 🤝 Contributing

Contributions are welcome.

You can contribute by:

- Reporting bugs
- Improving documentation
- Improving installation scripts
- Improving Termux compatibility
- Improving configuration handling
- Adding useful features
- Fixing issues
- Submitting pull requests

Before submitting a pull request, test your changes in a real Termux environment when possible.

---

## ⭐ Support

If you find the project useful, you can support it by:

- ⭐ Starring the repository
- 🐛 Reporting bugs
- 💡 Suggesting features
- 🔧 Contributing code
- 📖 Improving the documentation

---

## ⚠️ Disclaimer

This project is provided for educational, development, and legitimate networking purposes.

Users are responsible for complying with the laws, regulations, network policies, and terms of service applicable to their environment.

The project does not guarantee compatibility or performance on every Android device, network, server, or Xray configuration.

---

## 📄 License

This project is licensed under the **MIT License**.

See the [`LICENSE`](LICENSE) file for the complete license text.

---

## 👤 Author

Created and maintained by **sepantartd**.

GitHub:

https://github.com/sepantartd

---

## 🔗 Repository

https://github.com/sepantartd/v2ray-termux
