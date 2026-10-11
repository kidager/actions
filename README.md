# actions

Shared GitHub Actions for the kidager repositories.

## token

Gets a kidager-bot token for the current repository, so the next steps act as kidager[bot]. The job needs `id-token: write`.

```yaml
permissions:
  id-token: write

steps:
  - id: bot
    uses: kidager/actions/token@<sha> # v0.1.0
  - uses: marocchino/sticky-pull-request-comment@<sha>
    with:
      GITHUB_TOKEN: ${{ steps.bot.outputs.token }}
      message: Hello
```

Other permissions: `with: { permissions: '{"contents": "write"}' }`.

## License

[UNLICENSE](https://unlicense.org/)
