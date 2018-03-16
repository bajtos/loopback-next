# loopback-next

[![Gitter](https://img.shields.io/gitter/room/nwjs/nw.js.svg)](https://gitter.im/strongloop/loopback) [![Travis Build Status](https://img.shields.io/travis/rust-lang/rust.svg)](https://travis-ci.org/strongloop/loopback-next) [![AppVeyor Build status](https://ci.appveyor.com/api/projects/status/3v1qmusv168a0kb0/branch/master?svg=true)](https://ci.appveyor.com/project/bajtos/loopback-next/branch/master) [![Coverage Status](https://coveralls.io/repos/github/strongloop/loopback-next/badge.svg?branch=master)](https://coveralls.io/github/strongloop/loopback-next?branch=master)

LoopBack makes it easy to build modern applications that require complex integrations.

- Fast, small, powerful, extensible core
- Generate real APIs with a single command
- Define your data and endpoints with OpenAPI
- No maintenance of generated code

# Status: Developer Preview #1

LoopBack 4 is a work in progress, the public API is frequently changed in
backwards-incompatible ways. See [Upcoming-Releases on wiki](https://github.com/strongloop/loopback-next/wiki/Upcoming-Releases)
for more details.

# Installation

Make sure you have the following installed:

- [Node.js](https://nodejs.org/en/download/) >= 8.0.0
- [TypeScript](https://www.typescriptlang.org/index.html#download-links) >= 2.5.0 `npm i -g typescript`

Then in your Node.js project root, run:

```shell
npm install -S @loopback/core
```

> Make sure you set `"target": "es2017"` in your compiler options in your
> `tsconfig.json` if you're using a TypeScript project. See [Installation
> ](http://loopback.io/doc/en/lb4/Installation.html) for
> detailed information.

# Example

A basic controller:

```ts
export class UserController {
  async getUserByName(username: string): Promise<UserResponse> {
    const users = new UserRepository();
    const user = await users.findOne({where: {username: username}});
    if (!user) {
      throw createHttpError.NotFound(`User ${username} not found.`);
    }
    return new UserResponse(user);
  }
}
```

To create your first LoopBack 4 application, See [Getting Started](http://loopback.io/doc/en/lb4/Getting-started.html).


# Documentation

- [Official documentation](http://loopback.io/doc/en/lb4/)
- [API documentation](http://apidocs.loopback.io/#LoopBack4)
- [FAQ](http://loopback.io/doc/en/lb4/FAQ.html)
- [LoopBack 3 vs LoopBack 4](http://loopback.io/doc/en/lb4/LoopBack-3.x.html)
- [Tutorials and examples](http://loopback.io/doc/en/lb4/Examples-and-tutorials.html)

# Contributing

See the following resources to get your started:

 - [Contributing Guidelines](./docs/CONTRIBUTING.md)
 - [Monorepo overview](./docs/site/MONOREPO.md)
 - [Developing LoopBack](./docs/site/DEVELOPING.md)

You can join the team by posting a comment to [issue #110](https://github.com/strongloop/loopback-next/issues/110.).

# Team

## Project Architects:

Raymond Feng|Miroslav Bajtos|Ritchie Martori
:-:|:-:|:-:
[<img src="https://avatars0.githubusercontent.com/u/540892?v=3&s=60">](http://github.com/raymondfeng)|[<img src="https://avatars2.githubusercontent.com/u/1140553?v=3&s=60">](http://github.com/bajtos)|[<img src="https://avatars2.githubusercontent.com/u/462228?v=3&s=60">](http://github.com/ritch)

## Project Maintainers:

|||||
|:-:|:-:|:-:|:-:|
|Taranveer Virk|Biniam Admikew|Kyu Shim|Diana Lau|
|[<img src="https://avatars1.githubusercontent.com/u/3311536?v=3&s=60">](http://github.com/virkt25)|[<img src="https://avatars0.githubusercontent.com/u/13950637?v=3&s=60">](http://github.com/b-admike)|[<img src="https://avatars3.githubusercontent.com/u/18518689?v=3&s=60" height=60>](http://github.com/shimks)|[<img src="https://avatars2.githubusercontent.com/u/25489897?v=3&s=60">](http://github.com/dhmlau)|
|Janny Hou|Simon Ho|Kevin Delisle|Rand McKinney|
|[<img src="https://avatars2.githubusercontent.com/u/12554153?v=3&s=60">](http://github.com/jannyHou)|[<img src="https://avatars1.githubusercontent.com/u/1617364?v=3&s=60">](http://github.com/superkhau)|[<img src="https://avatars3.githubusercontent.com/u/2053534?v=3&s=60">](http://github.com/kjdelisle)|[<img src="https://avatars2.githubusercontent.com/u/2925364?v=3&s=60">](http://github.com/crandmck)|

See [all contributors](https://github.com/strongloop/loopback-next/graphs/contributors).

# License

[MIT](LICENSE)
