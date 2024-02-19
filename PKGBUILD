# Maintainer: lilikoi <jamilbio20@gmail.com>
pkgname='chatgpt.sh'
pkgver=0.51.3
pkgrel=1
_commit=26237679f5fed135e68b8307b10bb0864161fec5
pkgdesc="Shell wrapper for OpenAI's ChatGPT, DALL-E, Whisper, and TTS. Features LocalAI, Ollama, and Google Gemini integration."
url='https://gitlab.com/fenixdragao/shellchatgpt'
arch=('any')
license=('GPL3')
provides=('chatgpt.sh')
depends=('bash' 'curl' 'jq')
makedepends=('git')
optdepends=(
	'imagemagick: edit input images'
	'xdg-utils: open images (xdg-open, open)'
	'sox: audio recorder (arecod, ffmpeg)'
	'mpv: audio player (sox, vlc, ffmpeg, afplay, play-audio)'
	'xsel: copy output to clipboard (xclip)'
	'python: count input tokens (tiktoken)'
	'bat: render markdown (pygmentize, glow, mdcat, mdless)'
	'w3m: dump url text (lynx, elinks, links)'
	#'coreutils: wrap output at spaces (fold)'
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
	#install -Dm644 "PKGBUILD" "$pkgdir/usr/share/doc/${pkgname}/PKGBUILD"
}
