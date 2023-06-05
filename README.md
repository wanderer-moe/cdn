<div align = "center">

# wanderer-moe/cdn

![CDN Response] ![CDN Response 24h] ![CDN Response 7d]

All the assets and other files for the CDN hosted at `cdn.wanderer.moe` - using **Cloudflare's R2 Storage**.

</div>

---

## Usage

### Github Actions

Configuration for Github Actions is stored in `.github/workflows/deploy.yml`.

- Each push to `main` will trigger deployment using `rclone` to the R2 Bucket, where the CDN is hosted.

### rclone & R2 Setup

The R2 bucket is synced using `rclone`.

- The `RCLONE_CONFIG` environment variable is used to store the configuration for `rclone` - this is stored in the Github repository secrets.

- If you are to use this repository to base your own R2 bucket off of, you will need to change the `rclone` configuration to your own:

```
[r2]
type = s3
provider = Cloudflare
access_key_id = <access_key_id>
secret_access_key = <secret_access_key>
endpoint = https://<bucket_name>.r2.cloudflarestorage.com/
acl = private
```

- The configuration above will give you access to all your R2 buckets, and will allow you to sync to them, you would specify like `r2:<bucket_name>` in the `rclone` command.

## Contributing

Make a pull request & [follow the template](pull_request_template.md) with any assets, games, etc you want to add to the CDN - it'll be reviewed and merged if it's appropriate.

- If you are to upload assets, please make sure the files are named appropriately such as `genshin-impact/splash-art/keqing-nobg.png`.

- If you're uploading a fanmade asset, it has to be **your own work, or you must have permission from the original creator.** (Please provide proof of this in the pull request) and it must be **clearly** stated in the file name, such as `genshin-impact/character-sheets/keqing-fanmade.png`.

- And, check for any conflicts (e.g files already existing with the same image / name)

## Authors

- [@dromzeh](https://www.github.com/dromzeh)

## License

`wanderer-moe/cdn` is licensed under the [GNU Affero General Public License v3.0](LICENCE) - **You must state all significant changes made to the original software, make the source code available to the public with credit to the original author, original source, and use the same license.**

[CDN Response]: https://img.shields.io/endpoint?label=CDN%20Response&style=for-the-badge&url=https%3A%2F%2Fraw.githubusercontent.com%2Fwanderer-moe%2Fstatus%2FHEAD%2Fapi%2Fcdn%2Fresponse-time.json
[CDN Response 24h]: https://img.shields.io/endpoint?label=CDN%20Response%20%2824h%29&style=for-the-badge&url=https%3A%2F%2Fraw.githubusercontent.com%2Fwanderer-moe%2Fstatus%2FHEAD%2Fapi%2Fcdn%2Fresponse-time-day.json
[CDN Response 7d]: https://img.shields.io/endpoint?label=CDN%20Response%20%281wk%29&style=for-the-badge&url=https%3A%2F%2Fraw.githubusercontent.com%2Fwanderer-moe%2Fstatus%2FHEAD%2Fapi%2Fcdn%2Fresponse-time-week.json