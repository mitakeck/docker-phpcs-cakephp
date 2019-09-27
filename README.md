# docker-phpcs-cakephp

phpcs with cakephp rule set

## Download

```bash
$ docker pull mitakeck/phpcs-cakephp
```

## Usage

```bash
$ docker run \
  -v /local/path/to/cakephp:/src \
  mitakeck/phpcs-cakephp [<options>]
```

```bash
$ cd {cakephp_root_dir}
$ docker run -v `pwd`:/src mitakeck/phpcs-cakephp src
```
