# zlib(libgen) searcher

[![GitHub stars](https://img.shields.io/github/stars/zu1k/zlib-searcher)](https://github.com/zu1k/zlib-searcher/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/zu1k/zlib-searcher)](https://github.com/zu1k/zlib-searcher/network)
[![Release](https://img.shields.io/github/release/zu1k/zlib-searcher)](https://github.com/zu1k/zlib-searcher/releases)
[![GitHub issues](https://img.shields.io/github/issues/zu1k/zlib-searcher)](https://github.com/zu1k/zlib-searcher/issues)
[![GitHub license](https://img.shields.io/github/license/zu1k/zlib-searcher)](https://github.com/zu1k/zlib-searcher/blob/master/LICENSE)

Search `zlib`/`libgen` index to get `ipfs_cid`.

We don't save and provide files, we provide search.

I hope everyone have a copy of the index locally, so that no need to rely on any centralized service.

## Usage

### 1. Download the pre-compiled binary from [Release](https://github.com/zu1k/zlib-searcher/releases).

Or you can compile by yourself.

### 2. Download the `index` file that has been created.

We will give the corresponding `index` download links for each version in the release page.

Or you can make your own via `bin/index.rs`.

Extract the `index` folder to the same level as the program, it should look like the following:

```
zlib_searcher_dir
├── index
│   ├── some index files...
│   └── meta.json
└── zlib-searcher
```

### 3. Run `zlib-searcher`, it will listen to `127.0.0.1:7070`.

Access http://127.0.0.1:7070/ to use webui, or you can use the original api.

#### original search api

You can search by the following fields:

- title
- author
- publisher
- extension
- language
- isbn
- zlib_id

Examples:

- `http://127.0.0.1:7070/search?limit=30&query=余华`
- `http://127.0.0.1:7070/search?limit=30&query=title:机器学习 extension:azw3 publisher:清华`
- `http://127.0.0.1:7070/search?limit=30&query=zlib_id:18557063`
- `http://127.0.0.1:7070/search?limit=30&query=isbn:9787302423287`

## Raw data

We downloaded `libgen` sql and `zlib` sql and exported the necessary data from them.

```
id, title, author, publisher, extension, filesize, language, year, pages, isbn, ipfs_cid
```

This raw data is used to generate our `index`, you can download the raw data from here:

- [zlib_index_books.csv.zip](https://zlib.r2.zu1k.com/raw/zlib_index_books.csv.zip)
- [libgen_index_books.csv.zip](https://zlib.r2.zu1k.com/raw/libgen_index_books.csv.zip)

## License

**zlib-searcher** © [zu1k](https://github.com/zu1k), Released under the [MIT](./LICENSE) License.<br>

> Blog [zu1k.com](https://zu1k.com) · GitHub [@zu1k](https://github.com/zu1k) · Twitter [@zu1k_lv](https://twitter.com/zu1k_lv) · Telegram Channel [@peekfun](https://t.me/peekfun)