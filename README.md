## win-cv-action

This is a github action to build opencv for windows and cache it.

It's intended to support gocv in static mode, and wraps the gocv windows setup script [here](https://github.com/hybridgroup/gocv/blob/release/win_build_opencv.cmd).

## Usage

```yml
on:
  ...

jobs:
  build:
    runs-on: windows-2019
    steps:
    - uses: viam-labs/win-cv-action
    - name: build module
      run: go build -tags opencvstatic .
```

The opencvstatic tag is from [here](https://github.com/hybridgroup/gocv/blob/beac0b62b8691dd8923627d14dc1559711649c7d/cgo_static_windows.go#L1) in gocv.
