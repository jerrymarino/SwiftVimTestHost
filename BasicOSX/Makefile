# In practice, we should be doing clean build.
all: clean
	mkdir -p .build
	xcodebuild -derivedDataPath $(PWD)/.build \
		-scheme  BasicOSX \
		| tee .build/last_build.log
	XCCompilationDB $(PWD)/.build/last_build.log
	echo "Checking compile commands"
	cat compile_commands.json || exit 1

clean:
	xcodebuild clean
