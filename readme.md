# Sensibo API for Go

Sensibo API implementation in Golang  
Fork from github.com/llun/sensibo-golang

Some changes was made to get more information about pods

## Usage

```go
package main

import (
	"fmt"

	"github.com/tskaard/sensibo-golang"
)

func main() {
	api := sensibo.NewSensibo("user-api-key")
	pods, err := api.GetPods()
	if err != nil {
		panic("Cannot get pods information from Sensibo")
	}

	for _, pod := range pods {
		states, err := api.GetAcStates(pod.ID)
		if err != nil {
			fmt.Println("Cannot get ac state")
			continue
		}

		fmt.Println(states)
	}
}
```

## License

MIT
