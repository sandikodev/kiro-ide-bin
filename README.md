# kiro-ide-bin

AUR package for [Kiro IDE](https://kiro.dev) — an agentic AI IDE with spec-driven development from prototype to production.

> **Status**: Pending listing on AUR. Install manually for now (see below).

## About

This package installs Kiro IDE from the **official upstream `.tar.gz`** provided by Amazon:

```
https://prod.download.desktop.kiro.dev/releases/stable/linux-x64/signed/$pkgver/tar/
```

- No `.deb` extraction — uses the upstream tar.gz directly
- Verifies download with Amazon's `certificate.pem` + `signature.bin`
- Installs to `/opt/Kiro` with symlink at `/usr/bin/kiro`
- Includes `.desktop` entries, shell completions (bash/zsh), and icon
- Auto-updates via GitHub Actions every 6 hours

## Installation

### Using paru (custom repo — recommended)

Add to `~/.config/paru/paru.conf`:

```ini
[sandikodev]
Url = https://github.com/sandikodev/kiro-ide-bin
```

Then:
```bash
paru -Sya
paru -S sandikodev/kiro-ide-bin
```

### Manual
```bash
git clone https://github.com/sandikodev/kiro-ide-bin.git
cd kiro-ide-bin
makepkg -si
```

### Once listed on AUR
```bash
yay -S kiro-ide-bin
paru -S kiro-ide-bin
```

## Checking for Updates

```bash
nvchecker -c .nvchecker.toml
# or
curl -s https://prod.download.desktop.kiro.dev/stable/metadata-linux-x64-stable.json | jq -r .currentRelease
```

## License

By installing Kiro IDE, you agree to:
- [AWS Customer Agreement](https://aws.amazon.com/agreement/)
- [AWS Intellectual Property License](https://aws.amazon.com/legal/aws-ip-license-terms/)
- [AWS Service Terms](https://aws.amazon.com/service-terms/)
- [AWS Privacy Notice](https://aws.amazon.com/privacy/)
