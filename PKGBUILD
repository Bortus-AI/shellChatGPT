# Maintainer: lilikoi <jamilbio20@gmail.com>
pkgname='chatgpt.sh'
pkgver=0.56
pkgrel=1
_commit=b715b182db4054667afe0942cfb3c709887aa435
pkgdesc="Shell wrapper for OpenAI's ChatGPT, DALL-E, Whisper, and TTS. Features LocalAI, Ollama, Gemini and Mistral integration."
url='https://gitlab.com/fenixdragao/shellchatgpt'
arch=('any')
license=('GPL3')
depends=('bash' 'curl' 'jq')
makedepends=('git')
optdepends=(
	'imagemagick: edit input images'
	'xdg-utils: open images (xdg-open, open)'
	'sox: audio recorder (arecod, ffmpeg)'
	'mpv: audio player (sox, vlc, ffmpeg, afplay)'
	'xsel: copy output to clipboard (xclip)'
	'python: modules (tiktoken, markdown, bs4)'
	'bat: render markdown (pygmentize, glow, mdcat, mdless)'
	'w3m: dump url text (lynx, elinks, links)'
)
source=("${pkgname}-${pkgver}::git+${url}.git#commit=${_commit}")
sha256sums=('SKIP')

package() {
	cd "${pkgname}-${pkgver}"
	install -Dm644 "LICENSE" "$pkgdir/usr/share/licenses/${pkgname}/LICENSE"
	install -Dm644 "man/${pkgname}.1" "${pkgdir}/usr/share/man/man1/${pkgname}.1"
	install -Dm644 "man/${pkgname}.txt" "$pkgdir/usr/share/doc/${pkgname}/${pkgname}.txt"
	install -Dm644 "man/${pkgname}.html" "$pkgdir/usr/share/doc/${pkgname}/${pkgname}.html"
	install -Dm644 "man/README.md" "$pkgdir/usr/share/doc/${pkgname}/${pkgname}.md"
	install -Dm644 "README.md" "$pkgdir/usr/share/doc/${pkgname}/README.md"
	install -Dm644 ".chatgpt.conf" "$pkgdir/usr/share/doc/${pkgname}/chatgpt.conf"
	install -Dm755 "${pkgname}" "${pkgdir}/usr/bin/${pkgname}"
}
