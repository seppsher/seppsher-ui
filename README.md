# @seppsher/ui

Reusable Angular components and utilities for forms and HTTP feedback.

## Build

Install dependencies and build the library:

```sh
npm install
npm run build
```

The package is generated in `dist/`.

## Private GitHub Packages registry

The package is published privately to GitHub Packages after a Release Please release is published. Releases are driven by Conventional Commits:

- `fix:` creates a patch release
- `feat:` creates a minor release
- A breaking change, marked with `!` (for example `feat!:`) or a `BREAKING CHANGE:` footer, creates a major release

Push commits to `main`; Release Please opens or updates a release pull request with the version and changelog. Merging that pull request creates a GitHub release and publishes the package automatically.

For the initial `0.1.0` release, create and publish a GitHub release tagged `v0.1.0` once the repository is set up. Later versions are released by merging the Release Please pull request. In the repository's Actions settings, allow GitHub Actions to create pull requests.

To install it in a consuming project, configure `.npmrc`:

```ini
@seppsher:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=${GITHUB_TOKEN}
```

Set `GITHUB_TOKEN` to a GitHub token with `read:packages` access. Do not commit the token. Then install the package:

```sh
npm install @seppsher/ui
```

## Public API

- `ReactiveFieldErrorsComponent` and `SignalFieldErrorsComponent`
- `LoaderComponent`
- `ScrollToFirstErrorDirective` and `scrollToFirstError`
- `REGEX`, `phoneValidator`, and `phoneSchema`
- `errorInterceptor` and `loaderInterceptor`
- `ErrorService` and `LoaderService`

The field error components use the `app-field-errors` selector and require Angular Material plus `@ngx-translate/core` in the consuming application. Translation keys use the `global.validation.*` namespace.
