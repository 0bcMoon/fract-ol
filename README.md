# fract-ol

An interactive fractal renderer written in C using MLX42 and GLFW. The main executable renders Mandelbrot and Julia sets; the bonus executable also includes the Burning Ship fractal.

## Requirements

- Make and a C compiler.
- MLX42 headers and library, plus GLFW.
- A graphical desktop session.

The Makefile expects dependencies under `$HOME/.brew`. If they are installed elsewhere, override `BREW` with the installation prefix containing `include/` and `lib/`:

```sh
make BREW=/path/to/prefix
```

MLX42 is not bundled with this repository. Its platform-specific linker requirements may require adjusting `MLX` in the Makefile. The recipes currently reference `CFALGS` while the variable is defined as `CFLAGS`, so the declared warning and optimization flags are not applied by those recipes.

## Run

Fractal names are case-sensitive.

```sh
./fractol Mandelbrot
./fractol Julia -0.7 0.27015
```

For the bonus version:

```sh
make bonus
./fractol_bonus ship
```

## Controls

For the main executable:

| Input | Action |
| --- | --- |
| Mouse wheel | Zoom in or out |
| `P` | Increase the iteration limit |
| `T` | Decrease the iteration limit |
| Escape | Exit |
| Resize window | Resize and redraw the image |

## Layout

- `src/`: Mandelbrot and Julia rendering, argument parsing, and main hooks.
- `bonus/`: bonus entry point, hooks, and Burning Ship rendering.
- `include/fractol.h`: shared types and declarations.

Use `make clean` to remove object files or `make fclean` to remove executables too.
