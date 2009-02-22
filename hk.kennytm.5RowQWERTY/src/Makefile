iPhoneDevPath=/Developer/Platforms/iPhoneOS.platform/Developer
iPhoneSDKPath=$(iPhoneDevPath)/SDKs/iPhoneOS2.2.sdk
iPhoneGCCIncPath=$(iPhoneSDKPath)/usr/lib/gcc/powerpc-apple-darwin9/4.0.1/include/
iKeyExIncPath=../../include
iKeyExLibPath=../../hk.kennytm.iKeyEx/deb/usr/lib
CMLSrcPath=../../hk.kennytm.Command/src

Compiler=$(iPhoneDevPath)/usr/bin/arm-apple-darwin9-gcc-4.0.1
CodeSign=ldid -S

Compiler=$(iPhoneDevPath)/usr/bin/arm-apple-darwin9-gcc-4.0.1

Options=-lobjc \
	-std=c99 \
	-I$(iPhoneSDKPath)/usr/include \
	-I$(iPhoneDevPath)/usr/include \
	-I$(iPhoneGCCIncPath) \
	-I$(iKeyExIncPath) \
	-F$(iPhoneSDKPath)/System/Library/Frameworks \
	-F$(iPhoneSDKPath)/System/Library/PrivateFrameworks \
	-framework Foundation \
	-framework UIKit \
	-framework CoreFoundation \
	-framework WebCore \
	-L$(iPhoneSDKPath)/usr/lib \
	-L$(iKeyExLibPath) \
	-Wall \
	-dynamiclib \
	-lobjc \
	-liKeyEx \
	-march=armv6 \
	-mcpu=arm1176jzf-s \
	-O3 \
	-mthumb \
	-liKeyEx \
	-init _init

Sources=5RowQWERTY.m $(CMLSrcPath)/CMLSelection.m
Target=../deb/Library/iKeyEx/Keyboards/5RowQWERTY.keyboard/5RowQWERTY

$(Target):	$(Sources)
	$(Compiler) $(Options) -o $@ $^
	$(CodeSign) $@

clean:
	rm $(Target)