# Memory Cache

A simple cache wrinting only with golang to storage itens on memory.

## How To Use

First step, install package

```bash
go get github.com/Conexao-solar/memorycache
# note if you have an error finished with status 128, run the following content
# that happens beause of cache is a private repo
git config --global url."git@github.com:".insteadOf "https://github.com/"
```

Declare your storage and create a *NewStorage*

```bash
import (
	"github.com/Conexao-solar/memorycache/memory"
	"github.com/Conexao-solar/memorycache"
)

var storage memorycache.Storage

func init() {
	storage = memory.NewStorage()
}

## add itens to storage

slcD := []string{"apple", "peach", "pear"}
slcB, _ := json.Marshal(slcD)

duration, _ := time.ParseDuration("6h")
storage.Set("key", slcB, duration)

## get itens

itens := storage.Get("key) //you receive a byte object -> {"apple", "peach", "pear"}
```
