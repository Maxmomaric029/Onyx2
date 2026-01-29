ARCHS = arm64
DEBUG = 0
FINALPACKAGE = 1
FOR_RELEASE = 1
IGNORE_WARNINGS = 1
THEOS_PACKAGE_SCHEME = rootless
TARGET = iphone:clang:latest:12.1

include $(THEOS)/makefiles/common.mk

TWEAK_NAME = FF

FF_FILES = ImGuiDrawView.mm \
           $(wildcard Security/*.mm) \
           $(wildcard Security/oxorany/*.cpp) \
           $(wildcard LoadView/*.mm) \
           $(wildcard LoadView/*.m) \
           $(wildcard imgui/*.cpp) \
           $(wildcard imgui/*.mm) \
           $(wildcard hook/*.c)

FF_FRAMEWORKS = UIKit Foundation Security QuartzCore CoreGraphics CoreText AVFoundation Accelerate GLKit SystemConfiguration GameController Metal MetalKit

FF_CCFLAGS = -std=c++11 -fno-rtti -fno-exceptions -DNDEBUG -fvisibility=hidden -w
FF_CFLAGS = -fobjc-arc -fvisibility=hidden -w

FF_INCLUDES = -I. -ISecurity -ILoadView -Iimgui -Ihook -IOther -IUtils

FF_CFLAGS += $(FF_INCLUDES)
FF_CCFLAGS += $(FF_INCLUDES)

include $(THEOS)/makefiles/tweak.mk