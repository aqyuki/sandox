.PHONY: all prepare
.DEFAULT_GOAL := all

all: prepare build objdump otool

prepare:
	@rm -rf dist
	@mkdir dist

build: main.go
	@go build -o dist/debug main.go
	@go build -ldflags "-s -w" -trimpath -o dist/release main.go

objdump: build
	@go tool objdump dist/debug > dist/objdump-debug.txt

otool: build
	@otool -a -h -l -v -V -t dist/debug > dist/otool-debug.txt
	@otool -a -h -l -v -V -t dist/release > dist/otool-release.txt
