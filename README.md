# AOS Test Kit Template

This is a simple github template repo that can be used to build and maintain AOS processes. 
It is setup to test locally out of the box, deploy when using trunk-based deployment.

## How it works?

You can create a new repo with this template and then utilize TDD to construct your AOS process, 
step by step, test by test. This workflow gives you a nice developer experience and an extremely
easy way to test and publish your code.

## First Test

In test/main.test.js after the load source test, create a test that designs a prompt function.

```js
test('create a prompt', async () => {
  const result = await Send({Action: 'Eval', Data: 'Prompt = function () return "hi> " end' })
  assert.equal(result.prompt, 'hi> ')
})
```

Save then run `npm t`

More Examples coming soon...

## Manually Deploy

```
npm i --no-fund -g https://get_ao.g8way.io
aos --load src/main.lua
```

## Deploy Setup

In you github repo, you need to setup a few secrets:

* Your Process Identifier `AOS`
* Your Deployment Key `KEYFILE` (you want to base64 encode it)

> NOTE: Don't have a deployment key, use `~/.aos.json`

## CONTRIBUTIONS

If you like this approach to building AOS processes, and have suggestions to make improves please
submit issues or PRs. But lets keep it simple and easy to use.

### Principles

* Should be easy to use
* Should emulate typing commands in the aos console
* Should make testing fun with AOS