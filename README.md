# A set of GitHub pages describing the status of various Qualcomm platforms.

## Testing it locally

- Install Ruby and bundler:

  ```bash
  sudo apt install bundler
  ```

- Setup bundler to use user path for all the storage:

  ```bash
  bundle config set --local path ~/.local/lib/
  ```

- Install all the dependencies:

  ```bash
  bundle install
  ```

- Just rebuild the data:
  ```
  ./regen.py
  bundle exec jekyll build
  ```
  Now you can check the HTML data built in `./_site/`.

- Or execute a local Jekyll server, providing an ongoing preview:

  ```bash
  bundle exec jekyll serve
  ```

  Now you can open [localhost:4000](http://127.0.0.1:4000/mainline-status/) with your Web
  browser. Jekyll will automatically regenerate the pages if any of the source
  files changes.

## Add new SoC / PMIC

Base your new file in either `./_soc/` or `./_pmic/` on `_soc.template` or
`_pmic.template` respectively. If those files do not exist yet in your tree,
call `./regen.py`!

For an SoC file you can additionally specify the key `pmic:` where you can
reference PMICs which are usually bundled with a given SoC.
