.PHONY: all
all:
	which swift-compilation-database
	# There is some issue with module versioning right now on newer toolchains
	swift build \
		-Xswiftc "-target" \
		-Xswiftc "x86_64-apple-macosx10.9" \
		-Xswiftc -parseable-output \
		2>&1 | swift-compilation-database
	cat compile_commands.json || exit 1
