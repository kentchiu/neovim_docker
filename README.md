# neovim_docker

Config neovim as PDE in docker

## Build

```bash
docker build -t kentchiu/pde --build-arg CACHEBUST=$(date +%s) . 
```

## Run


```bash
docker volume create pde
```

```bash
docker run -e TERM -e COLORTERM -e LC_ALL=C.UTF-8 -p 5173:5173 -p 4200:4200 -v pde:/root -v /home/kent/.ssh:/root/.ssh -ti kentchiu/pde
```


## Reset

```bash
docker rm -f $(docker ps -a -q)
docker volume rm -f pde
```


## TODO

- [x] command history
- [] focus on curren buffer when toggle nvim-tree
- [] code format (ts)
- [] code format not regrade to tab stops
- [] code indent not in position(ts)
- [x] keymap ft (find terminal) not work
- [x] keymap uw (toggle word wrap)
- [] search highlight (/)
- [x] jk not map to esc
- [] project scope diagnostics
