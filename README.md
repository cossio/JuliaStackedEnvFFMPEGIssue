julia --proj -e 'import Pkg; Pkg.instantiate()'

cd child_env
julia --proj -e 'import Pkg; Pkg.instantiate()'

export JULIA_LOAD_PATH=".:..:@stdlib"
julia --proj

julia> import Makie
