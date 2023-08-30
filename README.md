Example for https://github.com/MakieOrg/Makie.jl/issues/3123.

```
julia --proj -e 'import Pkg; Pkg.instantiate()'

cd child_env
julia --proj -e 'import Pkg; Pkg.instantiate()'

export JULIA_LOAD_PATH=".:..:@stdlib"
julia --proj

julia> import Makie
```

The line `JULIA_LOAD_PATH=".:..:@stdlib"` ensures that the only environments on the stack are the one at `child_env/Project.toml` and the one at the root of this repo.