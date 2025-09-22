**Package Installation**
> **Note:** The legacy `cisco-anyconnect` package is obsolete.  
⤷ Use **[Cisco Secure Client 5.x](https://aur.archlinux.org/packages/cisco-secure-client)**.

**Navigate to the desired directory where the repository will be cloned.**  
Use the `git clone` command followed by the URL of the repository:

```bash
git clone https://aur.archlinux.org/cisco-secure-client.git
```
Enter the **package directory** (newly cloned package folder):
```bash
cd cisco-secure-client
```
**Build and Install Package**   
Run `makepkg` within the package directory.   

⤷ `-s` (`--syncdeps`) flag will sync and install any missing dependencies required by PKGBUILD.  
⤷ `-i` (`--install`) flag will install the package file with pacman after compilation.
```bash
makepkg -si PKGBUILD
```
Running `makepkg PKGBUILD` without `-i`or `--insert` flag requires 
manual package file installation (`pacman -U pkgname-pkgver.pkg.tar.zst`):

```bash
sudo pacman -U cisco-secure-client-${pkgver}-${pkgrel}-x86_64.pkg.tar.zst
```

**Installed path:**  
`/opt/cisco/secureclient/bin/`