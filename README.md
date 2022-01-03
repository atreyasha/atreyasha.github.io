# atreyasha.github.io :microscope:

This repository documents a minimal personal website and blog powered by [Jekyll](https://jekyllrb.com/). The Jekyll theme used is adapted from [agusmakmun.github.io](https://github.com/agusmakmun/agusmakmun.github.io), which is distributed under the MIT [License](THIRD_PARTY_NOTICES.txt).

## Usage

To serve this website locally, follow the points below:

1. Install the core dependencies listed [here](https://jekyllrb.com/docs/installation/); particularly Ruby, RubyGems, GCC and Make

    **Note:** You might need to add a gems directory onto your `PATH` variable.

2. Install `jekyll` and `bundler` gems:

    ```
    $ gem install jekyll bundler
    ```

3. Clone this repository and navigate inside it

4. Install all necessary application `gems` automatically using `bundler`:

   ```
   $ bundle install
   ```

5. Build the site and serve it locally: 
   ```
   $ bundle exec jekyll serve
   ```

With your browser, open the local server address shown in the final command's output. This should normally default to `http://127.0.0.1:4000/`

## Troubleshooting

As per this [discussion](https://talk.jekyllrb.com/t/error-no-implicit-conversion-of-hash-into-integer/5890/2), Jekyll `v3.9` is incompatible with Ruby `v3`. Using these two together results in the `no implicit conversion of Hash into Integer (TypeError)` error message. Downgrading `ruby` to `v2.7.*` fixes the issue.
