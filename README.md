# Golang-Toast

[![license](https://img.shields.io/github/license/alphabyte02/go-toast)](https://github.com/alphabyte02/go-toast/blob/master/LICENSE)

cross-platform library for sending desktop notifications

## Installation

```shell script
go get github.com/AlphaBye02/go-toast
```

## Example

- Common invocation
  ```go
  package main
  
  import (
      "github.com/alphabyte02/go-toast"
  )
  
  func main() {
      // _ = toast.Push("test message")
      _ = toast.Push("test message", toast.WithTitle("app title"))
  }
  
  ```

- `macOS`
    ```go
    package main
    
    import (
        "github.com/alphabyte02/go-toast"
    )
    
    func main() {
        // _ = toast.Push("test message")
        // _ = toast.Push("test message", toast.WithTitle("app title"))
        _ = toast.Push("test message",
            toast.WithTitle("app title"),
            toast.WithSubtitle("app sub title"),
            toast.WithAudio(toast.Ping),
            // toast.WithObjectiveC(true),
        )
    }
    
    ```

- `Windows`
  ```go
  package main
  
  import (
      "github.com/alphabyte02/go-toast"
  )
  
  func main() {
      // _ = toast.Push("test message")
      // _ = toast.Push("test message", toast.WithTitle("app title"))
      _ = toast.Push("test message",
          toast.WithTitle("app title"),
          toast.WithAppID("app id"),
          toast.WithAudio(toast.Default),
          toast.WithLongDuration(),
          toast.WithIcon("/path/icon.png"),
      )
      // bs, err := os.ReadFile("/path/icon.png")
      // if err != nil {
      // 	log.Fatalln(err)
      // }
      // toast.WithIconRaw(bs)
  }
  
  ```

- `js && wasm`
  ```go
  package main
  
  import (
      "fmt"
      "github.com/alphabyte02/go-toast"
  )
  
  func main() {
      // _ = toast.Push("test message")
      // _ = toast.Push("test message", toast.WithTitle("app title"))
      _ = toast.Push("test_message",
          toast.WithTitle("GO-WASM-APP"),
          toast.WithOnClick(func(event interface{}) {
              fmt.Println("click")
          }),
          toast.WithOnClose(func() {
              fmt.Println("close")
          }),
          toast.WithOnShow(func() {
              fmt.Println("show")
          }),
      )
  }
    
  ```

## Thanks

Thank you [JetBrains](https://www.jetbrains.com/?from=gwda) for providing free open source licenses

---

Repository|Description
---|---
|[go-toast/toast](https://github.com/go-toast/toast)|A go package for Windows 10 toast notifications|
|[fyne-io/fyne](https://github.com/fyne-io/fyne)|Cross platform GUI in Go inspired by Material Design|
|[gen2brain/beeep](https://github.com/gen2brain/beeep)|Go cross-platform library for sending desktop notifications, alerts and beeps|
|[julienXX/terminal-notifier](https://github.com/julienXX/terminal-notifier)|Send User Notifications on macOS from the command-line.|
|[variadico/noti](https://github.com/variadico/noti)|Monitor a process and trigger a notification.|
