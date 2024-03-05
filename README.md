mkdir setup && cd setup && git clone https://chromium.googlesource.com/chromium/tools/depot_tools.git
nano ~/.bashrc
 at the end of the file append
export PATH="$PATH:/workspace/Chromium/setup/depot_tools"

<!-- git clone https://chromium.googlesource.com/chromium.git -->

git config --global core.precomposeUnicode true

mkdir ./chromium && cd ./chromium
fetch --nohooks --no-history chromium
cd src/
./build/install-build-deps.sh
gn gen out/Default
autoninja -C out/Default chrome


sudo find / -type d -name "gn" 2>/dev/null 