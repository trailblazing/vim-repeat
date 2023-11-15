# repeat.vim

If you've ever tried using the `.` command after a plugin map, you were
likely disappointed to discover it only repeated the last native command
inside that map, rather than the map as a whole.  That disappointment
ends today.  Repeat.vim remaps `.` in a way that plugins can tap into
it.

## Modification of this repo (trailblazing/vim-repeat):

Using \<c-u> as the Undo shortcut because I wanna a one-key PageUp: u

The following plugins support repeat.vim:

* [surround.vim](https://github.com/tpope/vim-surround)
* [speeddating.vim](https://github.com/tpope/vim-speeddating)
* [unimpaired.vim](https://github.com/tpope/vim-unimpaired)
* [vim-easyclip](https://github.com/svermeulen/vim-easyclip)
* [vim-radical](https://github.com/glts/vim-radical)

Adding support to a plugin is generally as simple as the following
command at the end of your map functions.

    silent! call repeat#set("\<Plug>MyWonderfulMap", v:count)

## Installation

Install using your favorite package manager, or use Vim's built-in package
support:

    mkdir -p ~/.vim/pack/what-ever-name/start
    cd ~/.vim/pack/what-ever-name/start
    git clone https://github.com/trailblazing/vim-repeat.git

    lazy.nvim
    [core.lua](https://raw.githubusercontent.com/trailblazing/dotconfig/master/init/editor/nvim/lua/plugins/core.lua)
    return {
        {
            "trailblazing/vim-repeat",
            event = "VeryLazy"
        },
    }

## Contributing

See the contribution guidelines for
[pathogen.vim](https://github.com/tpope/vim-pathogen#readme).

## Self-Promotion

Like repeat.vim? Follow the repository on
[GitHub](https://github.com/tpope/vim-repeat) and vote for it on
[vim.org](http://www.vim.org/scripts/script.php?script_id=2136).  And if
you're feeling especially charitable, follow [tpope](http://tpo.pe/) on
[Twitter](http://twitter.com/tpope) and
[GitHub](https://github.com/tpope).

## License

Copyright (c) Tim Pope.  Distributed under the same terms as Vim itself.
See `:help license`.
