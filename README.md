# 📸 Briefkasten Image Job

![GitHub Workflow Status](https://img.shields.io/github/workflow/status/ndom91/briefkasten-scrape/Playwright%20Fetch%20Images?label=job&style=flat-square)
[![Demo](https://img.shields.io/badge/demo-instance-green?style=flat-square)](https://briefkastenhq.com)

Job to periodically fetch missing bookmark screenshot cover photos. This Github Action uses Playwright to periodically fetch missing screenshots of saved Bookmarks.

See also:

- [Briefkasten App Demo](https://briefkastenhq.com)
- [Briefkasten App Repo](https://github.com/ndom91/briefkasten)
- [Briefkasten Extension Repo](https://github.com/ndom91/briefkasten-extension)

## 🚀 Getting Started

To run this yourself, you'll need a Github account and a few environment variables. These include a `DATABASE_URL` to your Briefkasten database. As well as the connection details to your image hosting service, in this case [ImageKit](https://imagekit.io).

1. Clone the repository

```sh
$ git clone https://github.com/Tuscan-blue/briefkasten-scrape.git
$ cd briefkasten-scrape
```

2. Copy `.env.example` to `.env` and edit the file `.env` accordingly

```sh
$ cp .env.example .env
$ vim .env
```
#### **File `.env.example` for reference**

```
DATABASE_URL=postgres://bkAdmin:briefkasten@postgres:5432/briefkasten?sslmode=disable

SUPABASE_KEY=
SUPABASE_URL=
SUPABASE_BUCKET_ID=

BOOKMARKS_CHUNK=10
```

3. Build Docker container

```sh
$ docker build . -t briefkasten-scrape:latest
```

This will execute and fetch the first 10 Bookmarks with missing cover images and attempt to capture them with Playwright. They will be uploaded to your image store of choice and then displayed for the user the next time they open their Briefkasten.

## 🏗 Contributing

Open to all contributions, please stick to formatting settings in your PR though!

## 📝 License

MIT
