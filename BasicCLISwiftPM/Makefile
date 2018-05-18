.PHONY: all
all:
	which swift-compilation-database
	swift build -v -Xswiftc -parseable-output 2>&1 | swift-compilation-database
