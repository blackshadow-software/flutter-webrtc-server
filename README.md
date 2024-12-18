# flutter-webrtc-server

## Fixed Version of the original flutter-webrtc-server

A simple WebRTC Signaling server for flutter-webrtc and html5.

Online Demo: `https://demo.cloudwebrtc.com:8086/`

## Features

- Support Windows/Linux/macOS
- Built-in web, signaling, [turn server](https://github.com/pion/turn/tree/master/examples/turn-server)
- Support [REST API For Access To TURN Services](https://tools.ietf.org/html/draft-uberti-behave-turn-rest-00)
- Use [flutter-webrtc-demo](https://github.com/cloudwebrtc/flutter-webrtc-demo) for all platforms.

## Usage

### Run from source

- Clone the repository. and open the project.

```bash
cd flutter-webrtc-server
```

- Use `mkcert` to create a self-signed certificate.

```bash
brew update
brew install mkcert
mkcert -key-file configs/certs/key.pem -cert-file configs/certs/cert.pem  localhost 127.0.0.1 ::1 0.0.0.0
```

- Run

```bash
brew install golang
go run cmd/server/main.go
```

- Open `https://0.0.0.0:8086` to use flutter web demo.
- If you need to test mobile app, please check the [webrtc-flutter-demo](https://github.com/cloudwebrtc/flutter-webrtc-demo).

## Note

Go to the `configs/config.ini` file to change the `TURN` server configuration. and you have to change the `public_ip` to your public IP or domain, and `username` and `password` to your own that will be used in the flutter app.

```ini
[turn]
public_ip=<YOUR PUBLIC IP/URL>
port=19302
realm=flutter-webrtc
username=<YOUR USER NAME>
password=<YOUR PASSWORD>
```
