# places-env-example

This is an example / demo project for [_places-env_](https://github.com/marckrenn/places-env) and its corresponding Github Action [_places-env-gha_](https://github.com/marckrenn/places-env-gha).

For more detailed information, please refer to [_places-env_'s readme](https://github.com/marckrenn/places-env/tree/main?tab=readme-ov-file), respectively [_places-env-gha_'s readme](https://github.com/marckrenn/places-env-gha/tree/main?tab=readme-ov-file).

## Usage – Local development

1. **Clone or fork this repo**

2. **Install _places-env_:**

- via [pypi](https://pypi.org/project/places-env/):

    `pip install places-env`

3. **Add crypto keys:**

- n the `.places`-folder create a folder called `keys`
- then create new files (with no file extension)

    | filename | content |
    |----------|---------|
    | `default` | `Xribeoxu5t7SYbsX/Y2qovmnihjFTyJBM7xaMuN5jq4=` |
    | `dev` | `k2c7pHpC3s+iaulDjFbopIHFYlaJukaebSe3Fth5ez4=` |
    | `prod` | `6rtRqrL+wz9TB85/Gl/bg4mEk8+bBShatAJiVNWbLgU=` |

- **Note:** These keys are only publicly shared for demo purposes. Usually, you wouldn't share them publicly!

4. **Decrypt `places.enc.yaml`**:

- either by executing [`places decrypt`](https://github.com/marckrenn/places-env/tree/main?tab=readme-ov-file#decrypt)
- or by by running [`places watch start (optionally: --daemon, --service)`](https://github.com/marckrenn/places-env/tree/main?tab=readme-ov-file#watch-start)

5. **Modify [`places.yaml`](https://github.com/marckrenn/places-env/tree/main?tab=readme-ov-file#placesyaml)**:
  - Use your preferred text editor  
  - Or modify it using the [_places-env_ CLI](https://github.com/marckrenn/places-env/tree/main?tab=readme-ov-file#places-cli-documentation)

6. **Track changes:**
  - Use [`places watch start (optionally: --daemon, --service)`](https://github.com/marckrenn/places-env/tree/main?tab=readme-ov-file#watch-start) (recommended)  
  - Alternatively, use [`places encrypt`](#encrypt) and [`places sync gitignore`](#sync-gitignore). This will automatically add all necessary entries to `.gitignore`.

7. **Generate environment files:**
  - If [`places watch start`](https://github.com/marckrenn/places-env/tree/main?tab=readme-ov-file#watch-start) is already running, environments with property `watch: true` will be (re)generated whenever [`places.yaml`](https://github.com/marckrenn/places-env/tree/main?tab=readme-ov-file#placesyaml) is updated.  
  - Or use [`places generate environment --all`](https://github.com/marckrenn/places-env/tree/main?tab=readme-ov-file#generate-environment) to manually regenerate all environment files.

8. **Commit modified [`places.enc.yaml`](#placesencyaml)**

## Usage – CI/CD Github Action

Please refer to [places-env github action example](.github/workflows/places-env.yaml), respectively [individual runs](https://github.com/marckrenn/places-env-example/actions/workflows/places-env.yaml) on how to use [_places-env-gha_](https://github.com/marckrenn/places-env-gha)

1. **Fork this repo**

2. **Trigger workflow:**
    - Go to `Action` → `places-env github action example` → `Run workflow`

3. **Use generated environment file downstream:**
    - After succesfully running [_places-env-gha_](https://github.com/marckrenn/places-env-gha), you can use the generated environment files downstream (eg. to ssh on a server, build a docker image etc.)**