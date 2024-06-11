<p align="center">
  <img src="logo.svg" width="200px" align="center" alt="Zod logo" />
  <h1 align="center">Zod</h1>
  <p align="center">
    ✨ <a href="https://zod.dev">https://zod.dev</a> ✨
    <br/>
    静的型推論による TypeScript ファーストのスキーマ検証
  </p>
</p>
<br/>
<p align="center">
<a href="https://github.com/colinhacks/zod/actions?query=branch%3Amain"><img src="https://github.com/colinhacks/zod/actions/workflows/test.yml/badge.svg?event=push&branch=main" alt="Zod CI status" /></a>
<a href="https://twitter.com/colinhacks" rel="nofollow"><img src="https://img.shields.io/badge/created%20by-@colinhacks-4BBAAB.svg" alt="Created by Colin McDonnell"></a>
<a href="https://opensource.org/licenses/MIT" rel="nofollow"><img src="https://img.shields.io/github/license/colinhacks/zod" alt="License"></a>
<a href="https://www.npmjs.com/package/zod" rel="nofollow"><img src="https://img.shields.io/npm/dw/zod.svg" alt="npm"></a>
<a href="https://www.npmjs.com/package/zod" rel="nofollow"><img src="https://img.shields.io/github/stars/colinhacks/zod" alt="stars"></a>
<a href="https://discord.gg/KaSRdyX2vc" rel="nofollow"><img src="https://img.shields.io/discord/893487829802418277?label=Discord&logo=discord&logoColor=white" alt="discord server"></a>
</p>

<div align="center">
  <a href="https://zod.dev">ドキュメント</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://discord.gg/RcG33DQJdf">Discord</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://www.npmjs.com/package/zod">npm</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://deno.land/x/zod">deno</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://github.com/colinhacks/zod/issues/new">Issues</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://twitter.com/colinhacks">@colinhacks</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://trpc.io">tRPC</a>
  <br />
</div>

<br/>
<br/>

## 目次

<!-- 完全なドキュメントは、[公式ドキュメントサイト](https://zod.js.org/) (推奨) と `README.md` の両方で入手できます。

#### [zod.js.org](https://zod.js.org) にアクセス >> -->

- [目次](#table-of-contents)
- [はじめに](#introduction)
  - [スポンサー](#sponsors)
    - [ゴールド](#gold)
    - [シルバー](#silver)
    - [ブロンズ](#bronze)
    - [カッパー](#copper)
  - [Ecosystem](#ecosystem)
    - [Resources](#resources)
    - [API libraries](#api-libraries)
    - [Form integrations](#form-integrations)
    - [Zod to X](#zod-to-x)
    - [X to Zod](#x-to-zod)
    - [Mocking](#mocking)
    - [Powered by Zod](#powered-by-zod)
    - [Utilities for Zod](#utilities-for-zod)
- [Installation](#installation)
  - [Requirements](#requirements)
  - [From `npm` (Node/Bun)](#from-npm-nodebun)
  - [From `deno.land/x` (Deno)](#from-denolandx-deno)
- [Basic usage](#basic-usage)
- [Primitives](#primitives)
- [Coercion for primitives](#coercion-for-primitives)
- [Literals](#literals)
- [Strings](#strings)
  - [Datetimes](#datetimes)
  - [Dates](#dates)
  - [Times](#times)
  - [IP addresses](#ip-addresses)
- [Numbers](#numbers)
- [BigInts](#bigints)
- [NaNs](#nans)
- [Booleans](#booleans)
- [Dates](#dates)
- [Zod enums](#zod-enums)
- [Native enums](#native-enums)
- [Optionals](#optionals)
- [Nullables](#nullables)
- [Objects](#objects)
  - [`.shape`](#shape)
  - [`.keyof`](#keyof)
  - [`.extend`](#extend)
  - [`.merge`](#merge)
  - [`.pick/.omit`](#pickomit)
  - [`.partial`](#partial)
  - [`.deepPartial`](#deeppartial)
  - [`.required`](#required)
  - [`.passthrough`](#passthrough)
  - [`.strict`](#strict)
  - [`.strip`](#strip)
  - [`.catchall`](#catchall)
- [Arrays](#arrays)
  - [`.element`](#element)
  - [`.nonempty`](#nonempty)
  - [`.min/.max/.length`](#minmaxlength)
- [Tuples](#tuples)
- [Unions](#unions)
- [Discriminated unions](#discriminated-unions)
- [Records](#records)
  - [Record key type](#record-key-type)
- [Maps](#maps)
- [Sets](#sets)
- [Intersections](#intersections)
- [Recursive types](#recursive-types)
  - [ZodType with ZodEffects](#zodtype-with-zodeffects)
  - [JSON type](#json-type)
  - [Cyclical objects](#cyclical-objects)
- [Promises](#promises)
- [Instanceof](#instanceof)
- [Functions](#functions)
- [Preprocess](#preprocess)
- [Custom schemas](#custom-schemas)
- [Schema methods](#schema-methods)
  - [`.parse`](#parse)
  - [`.parseAsync`](#parseasync)
  - [`.safeParse`](#safeparse)
  - [`.safeParseAsync`](#safeparseasync)
  - [`.refine`](#refine)
    - [Arguments](#arguments)
    - [Customize error path](#customize-error-path)
    - [Asynchronous refinements](#asynchronous-refinements)
    - [Relationship to transforms](#relationship-to-transforms)
  - [`.superRefine`](#superrefine)
    - [Abort early](#abort-early)
    - [Type refinements](#type-refinements)
  - [`.transform`](#transform)
    - [Chaining order](#chaining-order)
    - [Validating during transform](#validating-during-transform)
    - [Relationship to refinements](#relationship-to-refinements)
    - [Async transforms](#async-transforms)
  - [`.default`](#default)
  - [`.describe`](#describe)
  - [`.catch`](#catch)
  - [`.optional`](#optional)
  - [`.nullable`](#nullable)
  - [`.nullish`](#nullish)
  - [`.array`](#array)
  - [`.promise`](#promise)
  - [`.or`](#or)
  - [`.and`](#and)
  - [`.brand`](#brand)
  - [`.readonly`](#readonly)
  - [`.pipe`](#pipe)
    - [`.pipe()` で `z.coerce` の問題を修正](#you-can-use-pipe-to-fix-common-issues-with-zcoerce)
- [ガイドとコンセプト](#guides-and-concepts)
  - [型推論](#type-in​​ference)
  - [ジェネリック関数の記述](#writing-generic-functions)
    - [許容入力の制約](#constraining-allowable-inputs)
  - [エラー処理](#error-handling)
  - [エラーのフォーマット](#error-formatting)
- [比較](#comparison)
  - [Joi](#joi)
  - [Yup](#yup)
  - [io-ts](#io-ts)
  - [Runtypes](#runtypes)
  - [Ow](#ow)
- [変更履歴](#changelog)

## はじめに

Zod は、TypeScript ファーストのスキーマ宣言および検証ライブラリです。ここでは「スキーマ」という用語を、単純な `string` から複雑にネストされたオブジェクトまで、あらゆるデータ型を広く指すために使用しています。

Zod は、開発者にとって可能な限り使いやすいように設計されています。目標は、重複する型宣言を取り除くことです。Zod を使用すると、バリデーションを１回宣言するだけで、Zod が自動的に静的な TypeScript 型を推測します。より単純な型を複雑なデータ構造に組み込むのは簡単です。

その他の素晴らしい点

- 依存関係ゼロ
- Node.js とすべての最新ブラウザで動作します
- 極小: 8kb 縮小 + 圧縮
- 不変: メソッド (例: `.optional()`) は新しいインスタンスを返します
- 簡潔で連鎖可能なインターフェース
- 関数型アプローチ: [解析するが検証しない](https://lexi-lambda.github.io/blog/2019/11/05/parse-don-t-validate/)
- プレーンな JavaScript でも動作します。TypeScript を使用する必要はありません。

## スポンサー

あらゆるレベルのスポンサーシップは歓迎され、奨励されています。個人開発者の場合は、[Cup of Coffee](https://github.com/sponsors/colinhacks) を検討してください。Zod を使用して有料製品を構築した場合は、[podium](https://github.com/sponsors/colinhacks) のいずれかを検討してください。

<h3 align="center">プラチナ</h3>

<blockquote align="center" width="400px">
  Zod のプラチナスポンサーになる方法については、<a href="mailto:colin@colinhacks.com" target="_blank">メール</a> にてご連絡ください。
</blockquote>

<!-- <table>
  <tr>
    <td align="center">
      <a href="https://www.example.com" target="_blank">
        <img src="https://example.com/image.png" height="100px;" alt="XXX" />
      </a>
      <br />
      <b>XXX</b>
      <br />
      <a href="https://www.example.com" target="_blank">example.com</a>
    </td>
  </tr>
</table> -->

<h3 align="center">ゴールド</h3>

<table align="center">
  <tr>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/89474619?s=200&v=4" height="50px;" alt="PropelAuth" />
      <br />
      <a style="text-decoration:none;" href="https://www.propelauth.com/" target="_blank">PropelAuth</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/80861386?s=200&v=4" height="50px;" alt="Cerbos" />
      <br />
      <a style="text-decoration:none;" href="https://cerbos.dev/" target="_blank">Cerbos</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/301879?s=200&v=4" height="50px;" alt="Scalar.com logo" />
      <br />
      <a style="text-decoration:none;" href="https://scalar.com/" target="_blank">Scalar</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/91446104?s=200&v=4" height="50px;" alt="Speakeasy API" />
      <br />
      <a style="text-decoration:none;" href="https://speakeasyapi.dev/" target="_blank">Speakeasy</a>
    </td>
    </tr><tr>
    <td align="center">
      <img src="https://avatars0.githubusercontent.com/u/15068039?s=200&v=4" height="50px;" alt="Deletype logo" />
      <br />
      <a style="text-decoration:none;" href="https://deletype.com" target="_blank">Deletype</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/95297378?s=200&v=4" height="50px;" alt="Trigger.dev logo" />
      <br />
      <a style="text-decoration:none;" href="https://trigger.dev" target="_blank">Trigger.dev</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/125754?s=200&v=4" height="50px;" alt="Transloadit logo" />
      <br />
      <a style="text-decoration:none;" href="https://transloadit.com/?utm_source=zod&utm_medium=refe
    rral&utm_campaign=sponsorship&utm_content=github" target="_blank">Transloadit</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/107880645?s=200&v=4" height="50px;" alt="Infisical logo" />
      <br />
      <a style="text-decoration:none;" href="https://infisical.com" target="_blank">Infisical</a>
    </td>
    </tr><tr>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/91036480?s=200&v=4" height="50px;" alt="Whop logo" />
      <br />
      <a style="text-decoration:none;" href="https://whop.com/" target="_blank">Whop</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/36402888?s=200&v=4" height="50px;" alt="CryptoJobsList logo" />
      <br />
      <a style="text-decoration:none;" href="https://cryptojobslist.com/" target="_blank">CryptoJobsList</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/70170949?s=200&v=4" height="50px;" alt="Plain logo" />
      <br />
      <a style="text-decoration:none;" href="https://plain.com/" target="_blank">Plain.</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/78935958?s=200&v=4" height="50px;" alt="Inngest logo" />
      <br />
      <a style="text-decoration:none;" href="https://inngest.com/" target="_blank">Inngest</a>
    </td>
  </tr><tr>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/13880908?s=200&v=4" height="50px;" alt="Storyblok CMS" />
      <br />
      <a style="text-decoration:none;" href="https://storyblok.com/" target="_blank">Storyblok</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/16199997?s=200&v=4" height="50px;" alt="Mux logo" />
      <br />
      <a style="text-decoration:none;" href="https://mux.link/zod" target="_blank">Mux</a>
    </td>
    <td align="center">
      <img src="https://avatars.githubusercontent.com/u/180984?v=4" height="50px;" alt="@emreb" />
      <br />
      <a style="text-decoration:none;" href="https://github.com/emreb" target="_blank"><code>@emreb</code></a>
    </td>
  </tr>
</table>

<h3 align="center">シルバー</h3>

<table align="center">
  <tr>
    <td align="center">
      <a href="https://encore.dev">
        <img src="https://github.com/colinhacks/zod/assets/3084745/5ad94e73-cd34-4957-9979-37da85fcf9cd" height="40px;" alt="Encore.dev logo" />
      </a>
    </td>
    <td align="center">
      <a href="https://www.replay.io/">
        <img src="https://avatars.githubusercontent.com/u/60818315?s=200&v=4" height="40px;" alt="Replay.io logo" />
      </a>
    </td>
    <td align="center">
      <a href="https://www.numeric.io">
        <img src="https://i.imgur.com/kTiLtZt.png" height="40px;" alt="Numeric logo" />
      </a>
    </td>
    <td align="center">
      <a href="https://marcatopartners.com">
        <img src="https://avatars.githubusercontent.com/u/84106192?s=200&v=4" height="40px;" alt="Marcato Partners" />
      </a>
    </td>
  </tr>
  <tr>
    <td align="center">
      <a href="https://interval.com">
        <img src="https://avatars.githubusercontent.com/u/67802063?s=200&v=4" height="40px;" alt="" />
      </a>
    </td>
    <td align="center">
      <a href="https://seasoned.cc">
        <img src="https://avatars.githubusercontent.com/u/33913103?s=200&v=4" height="40px;" alt="" />
      </a>
    </td>
    <td align="center">
      <a href="https://www.bamboocreative.nz/">
        <img src="https://avatars.githubusercontent.com/u/41406870?v=4" height="40px;" alt="Bamboo Creative logo" />
      </a>
    </td>
  </tr>
</table>

<h3 align="center">ブロンズ</h3>

<table align="center">
  <tr>
    <td>Brandon Bayer</td>
    <td>Jiří Brabec</td>
    <td>Alex Johansson</td>
    <td>Fungible Systems</td>
  </tr>
  <tr>
    <td>Adaptable</td>
    <td>Avana Wallet</td>
    <td>Jason Lengstorf</td>
    <td>Global Illumination, Inc.</td>
  </tr>
  <tr>
    <td>MasterBorn</td>
    <td>Ryan Palmer</td>
    <td>Michael Sweeney</td>
    <td>Nextbase</td>
  </tr>
  <tr>
    <td>Remotion</td>
    <td>Connor Sinnott</td>
    <td>Mohammad-Ali A'râbi</td>
    <td>Supatool</td>
  </tr>
</table>

### エコシステム

Zod で構築されているツールや、Zod をネイティブにサポートするツールの数は増えています。もし、Zod をベースにツールやライブラリを構築したことがある場合は、[Twitter](https://twitter.com/colinhacks) で教えてください。または、[ディスカッションを開始](https://github.com/colinhacks/zod/discussions) してくださいね。以下の一覧に追加したり、ツイートもしたいと思います。

#### リソース

- [Total TypeScript Zod Tutorial](https://www.totaltypescript.com/tutorials/zod) by [@mattpocockuk](https://twitter.com/mattpocockuk)
- [Fixing TypeScript's Blindspot: Runtime Typechecking](https://www.youtube.com/watch?v=rY_XqfSHock) by [@jherr](https://twitter.com/jherr)

#### API ライブラリ

- [`tRPC`](https://github.com/trpc/trpc): Build end-to-end typesafe APIs without GraphQL.
- [`@anatine/zod-nestjs`](https://github.com/anatine/zod-plugins/tree/main/packages/zod-nestjs): Helper methods for using Zod in a NestJS project.
- [`zod-endpoints`](https://github.com/flock-community/zod-endpoints): Contract-first strictly typed endpoints with Zod. OpenAPI compatible.
- [`zhttp`](https://github.com/evertdespiegeleer/zhttp): An OpenAPI compatible, strictly typed http library with Zod input and response validation.
- [`domain-functions`](https://github.com/SeasonedSoftware/domain-functions/): Decouple your business logic from your framework using composable functions. With first-class type inference from end to end powered by Zod schemas.
- [`@zodios/core`](https://github.com/ecyrbe/zodios): axios と zod に支えられた実行時およびコンパイル時の検証を行う typescript API クライアント
- [`express-zod-api`](https://github.com/RobinTail/express-zod-api):  I/O スキーマ検証やカスタムミドルウェアを備えた Express ベースの API を構築
- [`tapiduck`](https://github.com/sumukhbarve/monoduck/blob/main/src/tapiduck/README.md): Zod と Express を使ったエンドツーエンドのタイプセーフ JSON API。少し tRPC に似ていますが、よりシンプルです
- [`koa-zod-router`](https://github.com/JakeFenley/koa-zod-router): Zod を使った I/O バリデーションで Koa にタイプセーフなルートを作成

#### Form integrations

- [`react-hook-form`](https://github.com/react-hook-form/resolvers#zod): A first-party Zod resolver for React Hook Form.
- [`zod-validation-error`](https://github.com/causaly/zod-validation-error): Generate user-friendly error messages from `ZodError`s.
- [`zod-formik-adapter`](https://github.com/robertLichtnow/zod-formik-adapter): A community-maintained Formik adapter for Zod.
- [`react-zorm`](https://github.com/esamattis/react-zorm): Standalone `<form>` generation and validation for React using Zod.
- [`zodix`](https://github.com/rileytomasek/zodix): Zod utilities for FormData and URLSearchParams in Remix loaders and actions.
- [`conform`](https://conform.guide/api/zod/parseWithZod): A typesafe form validation library for progressive enhancement of HTML forms. Works with Remix and Next.js.
- [`remix-params-helper`](https://github.com/kiliman/remix-params-helper): Simplify integration of Zod with standard URLSearchParams and FormData for Remix apps.
- [`formik-validator-zod`](https://github.com/glazy/formik-validator-zod): Formik-compliant validator library that simplifies using Zod with Formik.
- [`zod-i18n-map`](https://github.com/aiji42/zod-i18n): Useful for translating Zod error messages.
- [`@modular-forms/solid`](https://github.com/fabian-hiller/modular-forms): Modular form library for SolidJS that supports Zod for validation.
- [`houseform`](https://github.com/crutchcorn/houseform/): A React form library that uses Zod for validation.
- [`sveltekit-superforms`](https://github.com/ciscoheat/sveltekit-superforms): Supercharged form library for SvelteKit with Zod validation.
- [`mobx-zod-form`](https://github.com/MonoidDev/mobx-zod-form): Data-first form builder based on MobX & Zod.
- [`@vee-validate/zod`](https://github.com/logaretm/vee-validate/tree/main/packages/zod): Form library for Vue.js with Zod schema validation.

#### Zod to X

- [`zod-to-ts`](https://github.com/sachinraja/zod-to-ts): Generate TypeScript definitions from Zod schemas.
- [`zod-to-json-schema`](https://github.com/StefanTerdell/zod-to-json-schema): Convert your Zod schemas into [JSON Schemas](https://json-schema.org/).
- [`@anatine/zod-openapi`](https://github.com/anatine/zod-plugins/tree/main/packages/zod-openapi): Converts a Zod schema to an OpenAPI v3.x `SchemaObject`.
- [`zod-fast-check`](https://github.com/DavidTimms/zod-fast-check): Generate `fast-check` arbitraries from Zod schemas.
- [`zod-dto`](https://github.com/kbkk/abitia/tree/main/packages/zod-dto): Generate Nest.js DTOs from a Zod schema.
- [`fastify-type-provider-zod`](https://github.com/turkerdev/fastify-type-provider-zod): Create Fastify type providers from Zod schemas.
- [`zod-to-openapi`](https://github.com/asteasolutions/zod-to-openapi): Generate full OpenAPI (Swagger) docs from Zod, including schemas, endpoints & parameters.
- [`nestjs-graphql-zod`](https://github.com/incetarik/nestjs-graphql-zod): Generates NestJS GraphQL model classes from Zod schemas. Provides GraphQL method decorators working with Zod schemas.
- [`zod-openapi`](https://github.com/samchungy/zod-openapi): Create full OpenAPI v3.x documentation from Zod schemas.
- [`fastify-zod-openapi`](https://github.com/samchungy/fastify-zod-openapi): Fastify type provider, validation, serialization and @fastify/swagger support for Zod schemas.
- [`typeschema`](https://typeschema.com/): Universal adapter for schema validation.

#### X to Zod

- [`ts-to-zod`](https://github.com/fabien0102/ts-to-zod): Convert TypeScript definitions into Zod schemas.
- [`@runtyping/zod`](https://github.com/johngeorgewright/runtyping/tree/main/packages/zod): Generate Zod from static types & JSON schema.
- [`json-schema-to-zod`](https://github.com/StefanTerdell/json-schema-to-zod): Convert your [JSON Schemas](https://json-schema.org/) into Zod schemas. [Live demo](https://StefanTerdell.github.io/json-schema-to-zod-react/).
- [`json-to-zod`](https://github.com/rsinohara/json-to-zod): Convert JSON objects into Zod schemas. [Live demo](https://rsinohara.github.io/json-to-zod-react/).
- [`graphql-codegen-typescript-validation-schema`](https://github.com/Code-Hex/graphql-codegen-typescript-validation-schema): GraphQL Code Generator plugin to generate form validation schema from your GraphQL schema.
- [`zod-prisma`](https://github.com/CarterGrimmeisen/zod-prisma): Generate Zod schemas from your Prisma schema.
- [`Supervillain`](https://github.com/Southclaws/supervillain): Generate Zod schemas from your Go structs.
- [`prisma-zod-generator`](https://github.com/omar-dulaimi/prisma-zod-generator): Emit Zod schemas from your Prisma schema.
- [`prisma-trpc-generator`](https://github.com/omar-dulaimi/prisma-trpc-generator): Emit fully implemented tRPC routers and their validation schemas using Zod.
- [`zod-prisma-types`](https://github.com/chrishoermann/zod-prisma-types) Create Zod types from your Prisma models.
- [`quicktype`](https://app.quicktype.io/): Convert JSON objects and JSON schemas into Zod schemas.
- [`@sanity-typed/zod`](https://github.com/saiichihashimoto/sanity-typed/tree/main/packages/zod): Generate Zod Schemas from [Sanity Schemas](https://www.sanity.io/docs/schema-types).
- [`java-to-zod`](https://github.com/ivangreene/java-to-zod): Convert POJOs to Zod schemas
- [`Orval`](https://github.com/anymaniax/orval): Generate Zod schemas from OpenAPI schemas
- [`Kubb`](https://github.com/kubb-labs/kubb): Generate SDKs and Zod schemas from your OpenAPI schemas

#### Mocking

- [`@anatine/zod-mock`](https://github.com/anatine/zod-plugins/tree/main/packages/zod-mock): Generate mock data from a Zod schema. Powered by [faker.js](https://github.com/faker-js/faker).
- [`zod-mocking`](https://github.com/dipasqualew/zod-mocking): Generate mock data from your Zod schemas.
- [`zod-fixture`](https://github.com/timdeschryver/zod-fixture): Use your zod schemas to automate the generation of non-relevant test fixtures in a deterministic way.
- [`zocker`](https://zocker.sigrist.dev): Generate plausible mock-data from your schemas.
- [`zodock`](https://github.com/ItMaga/zodock) Generate mock data based on Zod schemas.

#### Powered by Zod

- [`freerstore`](https://github.com/JacobWeisenburger/freerstore): Firestore cost optimizer.
- [`slonik`](https://github.com/gajus/slonik/tree/gajus/add-zod-validation-backwards-compatible#runtime-validation-and-static-type-inference): Node.js Postgres client with strong Zod integration.
- [`soly`](https://github.com/mdbetancourt/soly): Create CLI applications with zod.
- [`pastel`](https://github.com/vadimdemedes/pastel): Create CLI applications with react, zod, and ink.
- [`zod-xlsx`](https://github.com/sidwebworks/zod-xlsx): A xlsx based resource validator using Zod schemas.
- [`znv`](https://github.com/lostfictions/znv): Type-safe environment parsing and validation for Node.js with Zod schemas.
- [`zod-config`](https://github.com/alexmarqs/zod-config): Load configurations across multiple sources with flexible adapters, ensuring type safety with Zod.

#### Utilities for Zod

- [`zod_utilz`](https://github.com/JacobWeisenburger/zod_utilz): Framework agnostic utilities for Zod.
- [`zod-playground`](https://github.com/marilari88/zod-playground): A tool for learning and testing Zod schema validation functionalities. [Link](https://zod-playground.vercel.app/).
- [`zod-sandbox`](https://github.com/nereumelo/zod-sandbox): Controlled environment for testing zod schemas. [Live demo](https://zod-sandbox.vercel.app/).
- [`zod-dev`](https://github.com/schalkventer/zod-dev): Conditionally disables Zod runtime parsing in production.
- [`zod-accelerator`](https://github.com/duplojs/duplojs-zod-accelerator): Accelerates Zod's throughput up to ~100x.

## インストール

### 動作要件

- TypeScript 4.5 以上
- `tsconfig.json` で `strict` モードを有効にする必要があります。これはすべての TypeScript プロジェクトのベストプラクティスです。

  ```ts
  // tsconfig.json
  {
    // ...
    "compilerOptions": {
      // ...
      "strict": true
    }
  }
  ```

### `npm` (Node/Bun) からインストール

```sh
npm install zod       # npm
yarn add zod          # yarn
bun add zod           # bun
pnpm add zod          # pnpm
```

Zod はコミットごとにカナリアバージョンも公開しています。インストールするには以下をご覧ください。

```sh
npm install zod@canary       # npm
yarn add zod@canary          # yarn
bun add zod@canary           # bun
pnpm add zod@canary          # pnpm
```

### `deno.land/x` (Deno) よりインストール

Node とは異なり、Deno は NPM などのパッケージマネージャではなく、URLからの直接インポートを採用しています。Zod は [deno.land/x](https://deno.land/x) で入手できます。最新バージョンは次のようにインポートできます。

```ts
import { z } from "https://deno.land/x/zod/mod.ts";
```

特定のバージョンを指定することもできます。

```ts
import { z } from "https://deno.land/x/zod@v3.16.1/mod.ts";
```

> この README の残りの部分では、npm を使用して `"zod"` パッケージからインポートするのを前提としています。

## 基本的な使い方

シンプルな文字列スキーマの作成

```ts
import { z } from "zod";

// creating a schema for strings
const mySchema = z.string();

// parsing
mySchema.parse("tuna"); // => "tuna"
mySchema.parse(12); // => throws ZodError

// "safe" parsing (doesn't throw error if validation fails)
mySchema.safeParse("tuna"); // => { success: true; data: "tuna" }
mySchema.safeParse(12); // => { success: false; error: ZodError }
```

オブジェクトスキーマの作成

```ts
import { z } from "zod";

const User = z.object({
  username: z.string(),
});

User.parse({ username: "Ludwig" });

// extract the inferred type
type User = z.infer<typeof User>;
// { username: string }
```

## プリミティブ

```ts
import { z } from "zod";

// プリミティブ値
z.string();
z.number();
z.bigint();
z.boolean();
z.date();
z.symbol();

// 空の型
z.undefined();
z.null();
z.void(); // 未定義を許容

// キャッチオールな型
// 任意の値を許容
z.any();
z.unknown();

// 型を指定しない
// 値なしを許可
z.never();
```

## プリミティブの強制

Zod は、プリミティブ値を強制する便利な方法を提供するようになりました。

```ts
const schema = z.coerce.string();
schema.parse("tuna"); // => "tuna"
schema.parse(12); // => "12"
```

解析ステップでは、入力は `String()` 関数に渡されます。この関数は、データを文字列に強制変換するための JavaScript 組み込み関数です。

```ts
schema.parse(12); // => "12"
schema.parse(true); // => "true"
schema.parse(undefined); // => "undefined"
schema.parse(null); // => "null"
```

返されるスキーマは通常の `ZodString` インスタンスなので、すべての文字列メソッドを使用できます。

```ts
z.coerce.string().email().min(5);
```

**強制の仕組み**

すべてのプリミティブ型は強制変換をサポートしています。Zod は、組み込みコンストラクタの `String(input)`、`Number(input)`、`new Date(input)` などを使用して、すべての入力を強制変換します。

```ts
z.coerce.string(); // String(input)
z.coerce.number(); // Number(input)
z.coerce.boolean(); // Boolean(input)
z.coerce.bigint(); // BigInt(input)
z.coerce.date(); // new Date(input)
```

**注意** — `z.coerce.boolean()` を使用したブール値の強制変換は、期待どおりに動作しない可能性があります。[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) 値はすべて `true` に強制変換され、[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) 値はすべて `false` に強制変換されます。

```ts
const schema = z.coerce.boolean(); // Boolean(input)

schema.parse("tuna"); // => true
schema.parse("true"); // => true
schema.parse("false"); // => true
schema.parse(1); // => true
schema.parse([]); // => true

schema.parse(0); // => false
schema.parse(""); // => false
schema.parse(undefined); // => false
schema.parse(null); // => false
```

強制ロジックをさらに制御するには、[`z.preprocess`](#preprocess) または [`z.pipe()`](#pipe) の使用を検討してください。

## リテラル

リテラルスキーマは `"hello world"` や `5` のような [リテラル型](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#literal-types) を表します。

```ts
const tuna = z.literal("tuna");
const twelve = z.literal(12);
const twobig = z.literal(2n); // bigint literal
const tru = z.literal(true);

const terrificSymbol = Symbol("terrific");
const terrific = z.literal(terrificSymbol);

// retrieve literal value
tuna.value; // "tuna"
```

> 現在、Zod では日付リテラルをサポートしていません。この機能の使用例がある場合は、Issue を作成してください。

## 文字列

Zod には、文字列に関するバリデーションが多数用意されています。

```ts
// バリデーション
z.string().max(5);
z.string().min(5);
z.string().length(5);
z.string().email();
z.string().url();
z.string().emoji();
z.string().uuid();
z.string().nanoid();
z.string().cuid();
z.string().cuid2();
z.string().ulid();
z.string().regex(regex);
z.string().includes(string);
z.string().startsWith(string);
z.string().endsWith(string);
z.string().datetime(); // ISO 8601; デフォルトでは `Z` タイムゾーンのみが許可
z.string().ip(); // デフォルトでは IPv4 と IPv6 の両方を許可

// 変換
z.string().trim(); //  空白文字を除去
z.string().toLowerCase(); // 小文字にする
z.string().toUpperCase(); // 大文字にする

// Zod 3.23で追加
z.string().date(); // ISO 日付フォーマット (YYYY-MM-DD)
z.string().time(); // ISO 時間フォーマット (HH:mm:ss[.SSSSSS])
z.string().duration(); // ISO 8601 duration
z.string().base64();
```

> [Refinements](#refine) と組み合わせて使用できる便利な文字列バリデーション関数については、[validator.js](https://github.com/validatorjs/validator.js) を参照してください。

文字列スキーマを作成する際によく使用されるエラーメッセージをカスタマイズすることができます。

```ts
const name = z.string({
  required_error: "Name is required",
  invalid_type_error: "Name must be a string",
});
```

バリデーションメソッドを使用する際には、追加の引数を渡すことで、独自のエラーメッセージを指定することができます。

```ts
z.string().min(5, { message: "Must be 5 or more characters long" });
z.string().max(5, { message: "Must be 5 or fewer characters long" });
z.string().length(5, { message: "Must be exactly 5 characters long" });
z.string().email({ message: "Invalid email address" });
z.string().url({ message: "Invalid url" });
z.string().emoji({ message: "Contains non-emoji characters" });
z.string().uuid({ message: "Invalid UUID" });
z.string().includes("tuna", { message: "Must include tuna" });
z.string().startsWith("https://", { message: "Must provide secure URL" });
z.string().endsWith(".com", { message: "Only .com domains allowed" });
z.string().datetime({ message: "Invalid datetime string! Must be UTC." });
z.string().date({ message: "Invalid date string!" });
z.string().time({ message: "Invalid time string!" });
z.string().ip({ message: "Invalid IP address" });
```

### 日付と時刻

お気づきかもしれませんが、Zod 文字列には日付 / 時刻に関連するバリデーションがいくつか含まれています。これらのバリデーションは正規表現ベースなので、完全な日付 / 時刻ライブラリほど厳密ではありません。しかし、ユーザーの入力を検証するのに非常に便利です。

`z.string().datetime()` メソッドは ISO 8601 が適用されます。デフォルトは、タイムゾーンオフセットはなく、任意の秒未満の小数精度となります。

```ts
const datetime = z.string().datetime();

datetime.parse("2020-01-01T00:00:00Z"); // pass
datetime.parse("2020-01-01T00:00:00.123Z"); // pass
datetime.parse("2020-01-01T00:00:00.123456Z"); // pass (arbitrary precision)
datetime.parse("2020-01-01T00:00:00+02:00"); // fail (no offsets allowed)
```

`offset` オプションを `true` に設定することで、タイムゾーンオフセットを許可できます。

```ts
const datetime = z.string().datetime({ offset: true });

datetime.parse("2020-01-01T00:00:00+02:00"); // pass
datetime.parse("2020-01-01T00:00:00.123+02:00"); // pass (millis optional)
datetime.parse("2020-01-01T00:00:00.123+0200"); // pass (millis optional)
datetime.parse("2020-01-01T00:00:00.123+02"); // pass (only offset hours)
datetime.parse("2020-01-01T00:00:00Z"); // pass (Z still supported)
```

さらに、許容される `precision` （精度）を設定することもできます。デフォルトでは、任意の秒未満の精度がサポートされています（ただしオプション）。

```ts
const datetime = z.string().datetime({ precision: 3 });

datetime.parse("2020-01-01T00:00:00.123Z"); // pass
datetime.parse("2020-01-01T00:00:00Z"); // fail
datetime.parse("2020-01-01T00:00:00.123456Z"); // fail
```

### 日付

> Zod 3.23 で追加

`z.string().date()` メソッドは、`YYYY-MM-DD` 形式の文字列をバリデーションします。

```ts
const date = z.string().date();

date.parse("2020-01-01"); // pass
date.parse("2020-1-1"); // fail
date.parse("2020-01-32"); // fail
```

### 時刻

> Zod 3.23 で追加

`z.string().time()` メソッドは、`HH:MM:SS[.s+]` 形式の文字列をバリデーションします。秒には任意の小数精度を含めることもできます。このメソッドは、いかなるタイムゾーンオフセットも許可されません。

```ts
const time = z.string().time();

time.parse("00:00:00"); // pass
time.parse("09:52:31"); // pass
time.parse("23:59:59.9999999"); // pass (arbitrary precision)

time.parse("00:00:00.123Z"); // fail (no `Z` allowed)
time.parse("00:00:00.123+02:00"); // fail (no offsets allowed)
```

`precision` オプションを設定すると、許容される小数の精度を制御できます。

```ts
const time = z.string().time({ precision: 3 });

time.parse("00:00:00.123"); // pass
time.parse("00:00:00.123456"); // fail
time.parse("00:00:00"); // fail
```

### IP アドレス

`z.string().ip()` メソッドは、デフォルトで IPv4 と IPv6 をバリデーションします。

```ts
const ip = z.string().ip();

ip.parse("192.168.1.1"); // pass
ip.parse("84d5:51a0:9114:1855:4cfa:f2d7:1f12:7003"); // pass
ip.parse("84d5:51a0:9114:1855:4cfa:f2d7:1f12:192.168.1.1"); // pass

ip.parse("256.1.1.1"); // fail
ip.parse("84d5:51a0:9114:gggg:4cfa:f2d7:1f12:7003"); // fail
```

さらに IP の `バージョン` を設定することもできます。

```ts
const ipv4 = z.string().ip({ version: "v4" });
ipv4.parse("84d5:51a0:9114:1855:4cfa:f2d7:1f12:7003"); // fail

const ipv6 = z.string().ip({ version: "v6" });
ipv6.parse("192.168.1.1"); // fail
```

## 数値

数値スキーマを作成する際に、特定のエラーメッセージをカスタマイズすることができます。

```ts
const age = z.number({
  required_error: "Age is required",
  invalid_type_error: "Age must be a number",
});
```

Zod は数値に特化したバリデーションをいくつか用意しています。

```ts
z.number().gt(5);
z.number().gte(5); // alias .min(5)
z.number().lt(5);
z.number().lte(5); // alias .max(5)

z.number().int(); // value must be an integer

z.number().positive(); //     > 0
z.number().nonnegative(); //  >= 0
z.number().negative(); //     < 0
z.number().nonpositive(); //  <= 0

z.number().multipleOf(5); // Evenly divisible by 5. Alias .step(5)

z.number().finite(); // value must be finite, not Infinity or -Infinity
z.number().safe(); // value must be between Number.MIN_SAFE_INTEGER and Number.MAX_SAFE_INTEGER
```

オプションで、カスタムエラーメッセージを提供するために第2引数を渡すことができます

```ts
z.number().lte(5, { message: "this👏is👏too👏big" });
```

## BigInts

Zod には、bigint 専用のバリデーションがいくつか含まれています。

```ts
z.bigint().gt(5n);
z.bigint().gte(5n); // alias `.min(5n)`
z.bigint().lt(5n);
z.bigint().lte(5n); // alias `.max(5n)`

z.bigint().positive(); // > 0n
z.bigint().nonnegative(); // >= 0n
z.bigint().negative(); // < 0n
z.bigint().nonpositive(); // <= 0n

z.bigint().multipleOf(5n); // Evenly divisible by 5n.
```

## NaNs

nan スキーマを作成する際に、特定のエラーメッセージをカスタマイズすることができます。

```ts
const isNaN = z.nan({
  required_error: "isNaN is required",
  invalid_type_error: "isNaN must be 'not a number'",
});
```

## ブール値

ブール型のスキーマを作成する際に、特定のエラーメッセージをカスタマイズすることができます。

```ts
const isActive = z.boolean({
  required_error: "isActive is required",
  invalid_type_error: "isActive must be a boolean",
});
```

## 日付

z.date() を使用して、`Date` インスタンスをバリデーションします。 

```ts
z.date().safeParse(new Date()); // success: true
z.date().safeParse("2022-01-12T00:00:00.000Z"); // success: false
```

日付スキーマを作成する際に、特定のエラーメッセージをカスタマイズすることができます。

```ts
const myDateSchema = z.date({
  required_error: "Please select a date and time",
  invalid_type_error: "That's not a date!",
});
```

Zod は、日付に特化したバリデーションを提供しています。

```ts
z.date().min(new Date("1900-01-01"), { message: "Too old" });
z.date().max(new Date(), { message: "Too young!" });
```

**日付の強制**

[zod 3.20](https://github.com/colinhacks/zod/releases/tag/v3.20) 以降では、[`z.coerce.date()`](#coercion-for-primitives) を使用して、`new Date(input)`を通して入力を渡します。

```ts
const dateSchema = z.coerce.date();
type DateSchema = z.infer<typeof dateSchema>;
// type DateSchema = Date

/* valid dates */
console.log(dateSchema.safeParse("2023-01-10T00:00:00.000Z").success); // true
console.log(dateSchema.safeParse("2023-01-10").success); // true
console.log(dateSchema.safeParse("1/10/23").success); // true
console.log(dateSchema.safeParse(new Date("1/10/23")).success); // true

/* invalid dates */
console.log(dateSchema.safeParse("2023-13-10").success); // false
console.log(dateSchema.safeParse("0000-00-00").success); // false
```

古いバージョンの Zod の場合は [このスレッドで説明されている](https://github.com/colinhacks/zod/discussions/879#discussioncomment-2036276) のように、[`z.preprocess`](#preprocess)を使用してください。

## Zod 列挙型

```ts
const FishEnum = z.enum(["Salmon", "Tuna", "Trout"]);
type FishEnum = z.infer<typeof FishEnum>;
// 'Salmon' | 'Tuna' | 'Trout'
```

`z.enum` は、Zod ネイティブな方法で、許容される _string_ 値の固定セットを持つスキーマを宣言します。値の配列を `z.enum()` に直接渡します。また、`as const` を使用して、enum の値を文字列のタプルとして定義することもできます。詳細は [const アサーションドキュメント](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-4.html#const-assertions) を参照してください。

```ts
const VALUES = ["Salmon", "Tuna", "Trout"] as const;
const FishEnum = z.enum(VALUES);
```

Zod は各要素の正確な値を推測できないため、以下は許可されません。

```ts
const fish = ["Salmon", "Tuna", "Trout"];
const FishEnum = z.enum(fish);
```

**`.enum`**

Zod 列挙型で自動補完を行うには、スキーマの `.enum` プロパティを使用します。

```ts
FishEnum.enum.Salmon; // => autocompletes

FishEnum.enum;
/*
=> {
  Salmon: "Salmon",
  Tuna: "Tuna",
  Trout: "Trout",
}
*/
```

`.options` プロパティを使用して、オプションのリストをタプルとして取得することもできます。

```ts
FishEnum.options; // ["Salmon", "Tuna", "Trout"];
```

**`.exclude() と .extract()` メソッド**

`.exclude` メソッドと `.extract` メソッドを使用して Zod 列挙型のサブセットを作成できます。

```ts
const FishEnum = z.enum(["Salmon", "Tuna", "Trout"]);
const SalmonAndTrout = FishEnum.extract(["Salmon", "Trout"]);
const TunaOnly = FishEnum.exclude(["Salmon", "Trout"]);
```

## ネイティブ列挙型

Zod 列挙型は、列挙型を定義し検証するための推奨されるアプローチです。しかし、サードパーティライブラリの列挙型を検証する必要がある場合（あるいは既存の列挙型を書き換えたくない場合）は、`z.nativeEnum()` を使用できます。

**数値列挙型**

```ts
enum Fruits {
  Apple,
  Banana,
}

const FruitEnum = z.nativeEnum(Fruits);
type FruitEnum = z.infer<typeof FruitEnum>; // Fruits

FruitEnum.parse(Fruits.Apple); // passes
FruitEnum.parse(Fruits.Banana); // passes
FruitEnum.parse(0); // passes
FruitEnum.parse(1); // passes
FruitEnum.parse(3); // fails
```

**文字列列挙型**

```ts
enum Fruits {
  Apple = "apple",
  Banana = "banana",
  Cantaloupe, // you can mix numerical and string enums
}

const FruitEnum = z.nativeEnum(Fruits);
type FruitEnum = z.infer<typeof FruitEnum>; // Fruits

FruitEnum.parse(Fruits.Apple); // passes
FruitEnum.parse(Fruits.Cantaloupe); // passes
FruitEnum.parse("apple"); // passes
FruitEnum.parse("banana"); // passes
FruitEnum.parse(0); // passes
FruitEnum.parse("Cantaloupe"); // fails
```

**定数列挙型**

`.nativeEnum()` 関数は `as const` オブジェクトでも動作します。⚠️ `as const` には TypeScript 3.4 以上が必要です。

```ts
const Fruits = {
  Apple: "apple",
  Banana: "banana",
  Cantaloupe: 3,
} as const;

const FruitEnum = z.nativeEnum(Fruits);
type FruitEnum = z.infer<typeof FruitEnum>; // "apple" | "banana" | 3

FruitEnum.parse("apple"); // passes
FruitEnum.parse("banana"); // passes
FruitEnum.parse(3); // passes
FruitEnum.parse("Cantaloupe"); // fails
```

`.enum` プロパティを使用して、基礎となるオブジェクトにアクセスできます。

```ts
FruitEnum.enum.Apple; // "apple"
```

## オプション

`z.optional()` を使用するとで任意のスキーマをオプションにすることができます。スキーマを `ZodOptional` インスタンスでラップし、その結果を返します。

```ts
const schema = z.optional(z.string());

schema.parse(undefined); // => returns undefined
type A = z.infer<typeof schema>; // string | undefined
```

便宜上、既存のスキーマで `.optional()` メソッドを呼び出すこともできます。

```ts
const user = z.object({
  username: z.string().optional(),
});
type C = z.infer<typeof user>; // { username?: string | undefined };
```

`.unwrap()` を使用して、`ZodOptional` インスタンスからラップされたスキーマを抽出できます。

```ts
const stringSchema = z.string();
const optionalString = stringSchema.optional();
optionalString.unwrap() === stringSchema; // true
```

## Nullables

同様に、`z.nullable()` を使用して NULL 可能な型を作成できます。

```ts
const nullableString = z.nullable(z.string());
nullableString.parse("asdf"); // => "asdf"
nullableString.parse(null); // => null
```

または、`.nullable()` メソッドを使用します。

```ts
const E = z.string().nullable(); // equivalent to nullableString
type E = z.infer<typeof E>; // string | null
```

`.unwrap()` を使用して内部スキーマを抽出します。

```ts
const stringSchema = z.string();
const nullableString = stringSchema.nullable();
nullableString.unwrap() === stringSchema; // true
```

## オブジェクト

```ts
// all properties are required by default
const Dog = z.object({
  name: z.string(),
  age: z.number(),
});

// extract the inferred type like this
type Dog = z.infer<typeof Dog>;

// equivalent to:
type Dog = {
  name: string;
  age: number;
};
```

### `.shape`

特定のキーのスキーマにアクセスするには、`.shape` を使用します。

```ts
Dog.shape.name; // => string schema
Dog.shape.age; // => number schema
```

### `.keyof`

`.keyof` を使用して、オブジェクトスキーマのキーから `ZodEnum` スキーマを作成します。

```ts
const keySchema = Dog.keyof();
keySchema; // ZodEnum<["name", "age"]>
```

### `.extend`

`.extend` メソッドを使用して、オブジェクトスキーマにフィールドを追加します。

```ts
const DogWithBreed = Dog.extend({
  breed: z.string(),
});
```

`.extend` を使用するとフィールドを上書きすることができます。この機能には注意してください。

### `.merge`

`A.extend(B.shape)` と同等です。

```ts
const BaseTeacher = z.object({ students: z.array(z.string()) });
const HasID = z.object({ id: z.string() });

const Teacher = BaseTeacher.merge(HasID);
type Teacher = z.infer<typeof Teacher>; // => { students: string[], id: string }
```

> 2 つのスキーマがキーを共有する場合、B のプロパティは A のプロパティを上書きします。返されるスキーマは、B の「unknownKeys」ポリシー (strip/strict/passthrough) とキャッチオールスキーマも継承します。

### `.pick/.omit`

TypeScript 組み込みの `Pick` と `Omit` ユーティリティ型に触発され、すべての Zod オブジェクトスキーマは、変更されたバージョンを返す `.pick` メソッドと `.omit` メソッドがあります。次の Recipe スキーマについて見てみましょう。

```ts
const Recipe = z.object({
  id: z.string(),
  name: z.string(),
  ingredients: z.array(z.string()),
});
```

特定のキーのみを保持するには、 `.pick` を使用します。

```ts
const JustTheName = Recipe.pick({ name: true });
type JustTheName = z.infer<typeof JustTheName>;
// => { name: string }
```

特定のキーを削除するには、`.omit` を使用します。

```ts
const NoIDRecipe = Recipe.omit({ id: true });

type NoIDRecipe = z.infer<typeof NoIDRecipe>;
// => { name: string, ingredients: string[] }
```

### `.partial`

TypeScript 組み込みのユーティリティ型 [Partial](https://www.typescriptlang.org/docs/handbook/utility-types.html#partialtype) にヒントを得た `.partial` メソッドは、すべてのプロパティを **任意** とさせます。

次のオブジェクトから始めてみましょう。

```ts
const user = z.object({
  email: z.string(),
  username: z.string(),
});
// { email: string; username: string }
```

パーシャルなバージョンを作成してみましょう。

```ts
const partialUser = user.partial();
// { email?: string | undefined; username?: string | undefined }
```

任意にするプロパティを指定することもできます。

```ts
const optionalEmail = user.partial({
  email: true,
});
/*
{
  email?: string | undefined;
  username: string
}
*/
```

### `.deepPartial`

`.partial` メソッドは1階層分しか適用されない浅いメソッドです。深い階層に適応される `.deepPartial` バージョンもあります。

```ts
const user = z.object({
  username: z.string(),
  location: z.object({
    latitude: z.number(),
    longitude: z.number(),
  }),
  strings: z.array(z.object({ value: z.string() })),
});

const deepPartialUser = user.deepPartial();

/*
{
  username?: string | undefined,
  location?: {
    latitude?: number | undefined;
    longitude?: number | undefined;
  } | undefined,
  strings?: { value?: string}[]
}
*/
```

> 重要な制限：`.deepPartial` は、オブジェクト、配列、タプルの階層でのみ機能します。

### `.required`

`.partial` メソッドとは異なり、`.required` メソッドはすべてのプロパティを必須とします。

次のオブジェクトから始めてみましょう。

```ts
const user = z
  .object({
    email: z.string(),
    username: z.string(),
  })
  .partial();
// { email?: string | undefined; username?: string | undefined }
```

`.required` を付与してみましょう。

```ts
const requiredUser = user.required();
// { email: string; username: string }
```

必須となるプロパティを個別に指定することもできます。

```ts
const requiredEmail = user.required({
  email: true,
});
/*
{
  email: string;
  username?: string | undefined;
}
*/
```

### `.passthrough`

デフォルトでは、Zod オブジェクトスキーマは解析中に認識されないキーを削除します。

```ts
const person = z.object({
  name: z.string(),
});

person.parse({
  name: "bob dylan",
  extraKey: 61,
});
// => { name: "bob dylan" }
// extraKey has been stripped
```

代わりに、不明なキーでもパスする場合は `.passthrough()` を使用します。

```ts
person.passthrough().parse({
  name: "bob dylan",
  extraKey: 61,
});
// => { name: "bob dylan", extraKey: 61 }
```

### `.strict`

デフォルトでは、Zod オブジェクトスキーマは解析中に認識されないキーを削除します。`.strict()` を使用して、不明なキーを _禁止_ することができます。入力に不明なキーがある場合、Zod はエラーをスローします。

```ts
const person = z
  .object({
    name: z.string(),
  })
  .strict();

person.parse({
  name: "bob dylan",
  extraKey: 61,
});
// => throws ZodError
```

### `.strip`

`.strip` メソッドを使用すると、オブジェクトスキーマをデフォルトの動作（認識されないキーの削除）にリセットできます。

### `.catchall`

`catchall` スキーマをオブジェクトスキーマに渡すことができます。未知のキーはすべてこのスキーマでバリデーションされます。

```ts
const person = z
  .object({
    name: z.string(),
  })
  .catchall(z.number());

person.parse({
  name: "bob dylan",
  validExtraKey: 61, // works fine
});

person.parse({
  name: "bob dylan",
  validExtraKey: false, // fails
});
// => throws ZodError
```

`.catchall()` を使用すると、`.passthrough()`、`.strip()`、`.strict()` が不要になります。すべてのキーは「既知」と見なされます。

## 配列

```ts
const stringArray = z.array(z.string());

// equivalent
const stringArray = z.string().array();
```

`.array()` メソッドは注意して使用してください。新しい `ZodArray` インスタンスを返します。つまり、メソッドを呼び出す _順序_ が重要になります。次のような例をご覧ください。

```ts
z.string().optional().array(); // (string | undefined)[]
z.string().array().optional(); // string[] | undefined
```

### `.element`

配列要素のスキーマにアクセスするには、`.element` を使用します。

```ts
stringArray.element; // => string schema
```

### `.nonempty`

配列に少なくとも 1 つの要素が含まれていることを確認したい場合は、`.nonempty()` を使用します。

```ts
const nonEmptyStrings = z.string().array().nonempty();
// the inferred type is now
// [string, ...string[]]

nonEmptyStrings.parse([]); // throws: "Array cannot be empty"
nonEmptyStrings.parse(["Ariana Grande"]); // passes
```

オプションでカスタムエラーメッセージを設定できます。

```ts
// optional custom error message
const nonEmptyStrings = z.string().array().nonempty({
  message: "Can't be empty!",
});
```

### `.min/.max/.length`

```ts
z.string().array().min(5); // must contain 5 or more items
z.string().array().max(5); // must contain 5 or fewer items
z.string().array().length(5); // must contain 5 items exactly
```

`.nonempty()` とは異なり、これらのメソッドは推論された型を変更しません。

## タプル

配列とは異なり、タプルには固定数の要素があり、各要素は異なる型を持つことができます。

```ts
const athleteSchema = z.tuple([
  z.string(), // name
  z.number(), // jersey number
  z.object({
    pointsScored: z.number(),
  }), // statistics
]);

type Athlete = z.infer<typeof athleteSchema>;
// type Athlete = [string, number, { pointsScored: number }]
```

`.rest` メソッドを使用して、可変長引数 ("rest") を追加できます。

```ts
const variadicTuple = z.tuple([z.string()]).rest(z.number());
const result = variadicTuple.parse(["hello", 1, 2, 3]);
// => [string, ...number[]];
```

## ユニオン

Zod には、「OR」型を構成するための `z.union` 組み込みメソッドが含まれています。

```ts
const stringOrNumber = z.union([z.string(), z.number()]);

stringOrNumber.parse("foo"); // passes
stringOrNumber.parse(14); // passes
```

Zodは、各「オプション 」に対して入力を順番にテストし、バリデーションに成功した最初の値を返します。

便宜上、[`.or` メソッド](#or) も使用できます。

```ts
const stringOrNumber = z.string().or(z.number());
```

**オプションの文字列バリデーション**

オプションのフォーム入力をバリデーションするには、希望の文字列バリデーションを空の文字列 [literal](#literals) と結合することができます。

この例では、入力は任意だが [有効な URL](#strings) を含む必要がある入力のバリデーションを行います。

```ts
const optionalUrl = z.union([z.string().url().nullish(), z.literal("")]);

console.log(optionalUrl.safeParse(undefined).success); // true
console.log(optionalUrl.safeParse(null).success); // true
console.log(optionalUrl.safeParse("").success); // true
console.log(optionalUrl.safeParse("https://zod.dev").success); // true
console.log(optionalUrl.safeParse("not a valid url").success); // false
```

## 判別可能なユニオン

判別可能なユニオンは、特定のキーを共有するオブジェクトスキーマのユニオンです。

```ts
type MyUnion =
  | { status: "success"; data: string }
  | { status: "failed"; error: Error };
```

このようなユニオンは、`z.discriminatedUnion` メソッドで表すことができます。これにより、Zod は _discriminator key_ （上記の例では `status`）をチェックして、どのスキーマを使って入力を解析を判断できるため、高速な評価が可能になります。これにより、解析がより効率的になり、Zod はよりわかりやすいエラーを報告できるようになります。

基本的なユニオンメソッドでは、入力は指定された「オプション」のそれぞれに対してテストされ、無効の場合は、すべての「オプション」の問題が zod のエラーとして表示されます。一方、判別可能なユニオンは、「オプション」の 1 つだけを選択し、それに対してテストし、この「オプション」に関連する問題だけを表示することができます。

```ts
const myUnion = z.discriminatedUnion("status", [
  z.object({ status: z.literal("success"), data: z.string() }),
  z.object({ status: z.literal("failed"), error: z.instanceof(Error) }),
]);

myUnion.parse({ status: "success", data: "yippie ki yay" });
```

`.options` プロパティを使用して、スキーマの配列への参照を抽出できます。

```ts
myUnion.options; // [ZodObject<...>, ZodObject<...>]
```

2 つ以上の判別可能なユニオンをマージするには、デストラクチャリングで `.options` を使用します。

```ts
const A = z.discriminatedUnion("status", [
  /* options */
]);
const B = z.discriminatedUnion("status", [
  /* options */
]);

const AB = z.discriminatedUnion("status", [...A.options, ...B.options]);
```

## Records

レコードスキーマは `Record<string, number>` のような型をバリデーションするために使用されます。これは特に ID でアイテムを保存したりキャッシュしたりするのに便利です。

<!-- オブジェクトの _values_ をスキーマに照らして検証したいが、キーは気にしない場合は `z.record(valueType)` を使用すると良いでしょう。

```ts
const NumberCache = z.record(z.number());

type NumberCache = z.infer<typeof NumberCache>;
// => { [k: string]: number }
``` -->

```ts
const User = z.object({ name: z.string() });

const UserStore = z.record(z.string(), User);
type UserStore = z.infer<typeof UserStore>;
// => Record<string, { name: string }>
```

スキーマと推論された型は次のように使用できます。

```ts
const userStore: UserStore = {};

userStore["77d2586b-9e8e-4ecf-8b21-ea7e0530eadd"] = {
  name: "Carlotta",
}; // passes

userStore["77d2586b-9e8e-4ecf-8b21-ea7e0530eadd"] = {
  whatever: "Ice cream sundae",
}; // TypeError
```

**数字キーの注意**

`z.record(keyType, valueType)` は、数値のキー型を受け取ることができます。TypeScript 組み込みの Record 型は `Record<KeyType, ValueType>` ですが、TypeScript の型である `Record<number, any>` を Zod で表現するのは困難です。

結局のところ、TypeScript の `[k: number]` に関する動作は少し直感的ではありません。

```ts
const testMap: { [k: number]: string } = {
  1: "one",
};

for (const key in testMap) {
  console.log(`${key}: ${typeof key}`);
}
// prints: `1: string`
```

ご覧のとおり、JavaScript は内部ですべてのオブジェクトキーを文字列に自動的にキャストします。Zod はスタティック型とランタイム型の間のギャップを埋めようとしているため、ランタイム時の JavaScript には数値キーというものが存在しないため、数値キーでレコードスキーマを作成する方法は意味をなしません。

## Maps

```ts
const stringNumberMap = z.map(z.string(), z.number());

type StringNumberMap = z.infer<typeof stringNumberMap>;
// type StringNumberMap = Map<string, number>
```

## Sets

```ts
const numberSet = z.set(z.number());
type NumberSet = z.infer<typeof numberSet>;
// type NumberSet = Set<number>
```

set スキーマは以下のユーティリティメソッドでさらに細かく制約することができます。

```ts
z.set(z.string()).nonempty(); // must contain at least one item
z.set(z.string()).min(5); // must contain 5 or more items
z.set(z.string()).max(5); // must contain 5 or fewer items
z.set(z.string()).size(5); // must contain 5 items exactly
```

## Intersections

交差は、「論理 AND」型を作成する場合に便利です。これは、2 つのオブジェクトタイプを掛け合わせるのに便利です。

```ts
const Person = z.object({
  name: z.string(),
});

const Employee = z.object({
  role: z.string(),
});

const EmployedPerson = z.intersection(Person, Employee);

// equivalent to:
const EmployedPerson = Person.and(Employee);
```

多くの場合、2つのオブジェクトをマージするには `A.merge(B)` を使用することをお勧めします。`.merge` メソッドは新しい `ZodObject` インスタンスを返しますが、`A.and(B)` はあまり役に立たない `ZodIntersection` インスタンスを返します。このインスタンスには `pick` や `omit` といった一般的なオブジェクトメソッドがありません。

```ts
const a = z.union([z.number(), z.string()]);
const b = z.union([z.number(), z.boolean()]);
const c = z.intersection(a, b);

type c = z.infer<typeof c>; // => number
```

<!-- Zod の Intersection はスマートではありません。`.parse()` に渡したデータは、Intersection する 2 つのスキーマに渡されます。Zod オブジェクトスキーマは、デフォルトでは未知のキーを許可しないため、オブジェクトスキーマの Intersection には直感的でない振る舞いがあります。 -->

<!--

``` ts
const A = z.object({
  a: z.string(),
});

const B = z.object({
  b: z.string(),
});

const AB = z.intersection(A, B);

type Teacher = z.infer<typeof Teacher>;
// { id:string; name:string };
```  -->

## 再帰型

Zod では再帰的なスキーマを定義することができますが、TypeScript の制限により、その型を静的に推論することはできません。その代わりに、手動で型定義を行い、Zod に「型ヒント」として提示する必要があります。

```ts
const baseCategorySchema = z.object({
  name: z.string(),
});

type Category = z.infer<typeof baseCategorySchema> & {
  subcategories: Category[];
};

const categorySchema: z.ZodType<Category> = baseCategorySchema.extend({
  subcategories: z.lazy(() => categorySchema.array()),
});

categorySchema.parse({
  name: "People",
  subcategories: [
    {
      name: "Politicians",
      subcategories: [
        {
          name: "Presidents",
          subcategories: [],
        },
      ],
    },
  ],
}); // passes
```

この例を教えてくれた [crasite](https://github.com/crasite) に感謝いたします。

### ZodType と ZodEffects

`z.ZodType` を `z.ZodEffects` と一緒に使用する場合（[`.refine`](https://github.com/colinhacks/zod#refine)、[`.transform`](https://github.com/colinhacks/zod#transform)、[`preprocess`](https://github.com/colinhacks/zod#preprocess) 等） では、スキーマの入力と出力の型を定義する必要があります。`z.ZodType<Output, z.ZodTypeDef, Input>`

```ts
const isValidId = (id: string): id is `${string}/${string}` =>
  id.split("/").length === 2;

const baseSchema = z.object({
  id: z.string().refine(isValidId),
});

type Input = z.input<typeof baseSchema> & {
  children: Input[];
};

type Output = z.output<typeof baseSchema> & {
  children: Output[];
};

const schema: z.ZodType<Output, z.ZodTypeDef, Input> = baseSchema.extend({
  children: z.lazy(() => schema.array()),
});
```

この例を提供してくれた [marcus13371337](https://github.com/marcus13371337) と [JoelBeeldi](https://github.com/JoelBeeldi) に感謝します。

### JSON 型

任意の JSON 値をバリデーションする場合は、以下のスニペットを使用できます。

```ts
const literalSchema = z.union([z.string(), z.number(), z.boolean(), z.null()]);
type Literal = z.infer<typeof literalSchema>;
type Json = Literal | { [key: string]: Json } | Json[];
const jsonSchema: z.ZodType<Json> = z.lazy(() =>
  z.union([literalSchema, z.array(jsonSchema), z.record(jsonSchema)])
);

jsonSchema.parse(data);
```

これを提案してくれた [ggoodman](https://github.com/ggoodman) に感謝します。

### 周期的なオブジェクト

再帰的なスキーマをサポートしているにもかかわらず、周期的なデータを Zod に渡すと、場合によっては無限ループが発生してしまいます。

> 問題が発生する前に周期的なオブジェクトを検出するには、[このアプローチ](https://gist.github.com/colinhacks/d35825e505e635df27cc950776c5500b) を検討してください。

## Promises

```ts
const numberPromise = z.promise(z.number());
```

promise スキーマにおいて「parsing」は少し異なって動作します。バリデーションは２つのパートに分かれて行われます。

1. Zod は、入力が Promise のインスタンス (つまり、`.then` メソッドと `.catch` メソッドを持つオブジェクト) であることを同期的にチェックします。
2. Zod は `.then` を使用して、既存の Promise に追加の検証ステップを追加します。検証の失敗を処理するには、返された Promise で `.catch` を使用する必要があります。

```ts
numberPromise.parse("tuna");
// ZodError: Non-Promise type: string

numberPromise.parse(Promise.resolve("tuna"));
// => Promise<number>

const test = async () => {
  await numberPromise.parse(Promise.resolve("tuna"));
  // ZodError: Non-number type: string

  await numberPromise.parse(Promise.resolve(3.14));
  // => 3.14
};
```

<!-- #### 非ネイティブの Promise 実装

プロミスを「解析」するとき、Zod は渡された値が `.then` メソッドと `.catch` メソッドを持つオブジェクトであるかどうかをチェックします。それだけです。そのため、非ネイティブのプロミス（Bluebird など）を `z.promise(...).parse` に問題なく渡すことができます。1 つ注意点があります。parse 関数の戻り値の型はネイティブの `Promise` になるため、下流に非標準の Promise メソッドを使用するロジックがある場合、これは機能しません。 -->

## Instanceof

`z.instanceof` を使用すると、入力がクラスのインスタンスであることを確認できます。これは、サードパーティのライブラリからエクスポートされたクラスに対して入力を検証するのに役立ちます。

```ts
class Test {
  name: string;
}

const TestSchema = z.instanceof(Test);

const blob: any = "whatever";
TestSchema.parse(new Test()); // passes
TestSchema.parse(blob); // throws
```

## 関数スキーマ

Zod では「関数スキーマ」を定義することもできます。これにより、バリデーションコードと 「ビジネスロジック 」を混在させることなく、関数の入力と出力を簡単に検証できます。

`z.function(args, returnType)` を使用して関数スキーマを作成できます。

```ts
const myFunction = z.function();

type myFunction = z.infer<typeof myFunction>;
// => ()=>unknown
```

入力と出力を定義します。

```ts
const myFunction = z
  .function()
  .args(z.string(), z.number()) // accepts an arbitrary number of arguments
  .returns(z.boolean());

type myFunction = z.infer<typeof myFunction>;
// => (arg0: string, arg1: number)=>boolean
```

<!--

``` ts
const args = z.tuple([z.string()]);

const returnType = z.number();

const myFunction = z.function(args, returnType);
type myFunction = z.infer<typeof myFunction>;
// => (arg0: string)=>number
``` -->

関数スキーマには、関数を受け取って、その入出力を自動的に検証する新しい関数を返す `.implement()` メソッドがあります。

```ts
const trimmedLength = z
  .function()
  .args(z.string()) // accepts an arbitrary number of arguments
  .returns(z.number())
  .implement((x) => {
    // TypeScript knows x is a string!
    return x.trim().length;
  });

trimmedLength("sandwich"); // => 8
trimmedLength(" asdf "); // => 4
```

入力の検証のみを行うのであれば `.returns()` メソッドを呼び出さないでください。出力の型は実装から推測されます。

> 関数が何も返さない場合は、特別な `z.void()` オプションを使用できます。これにより、Zod は void を返す関数の型を適切に推測できるようになります。（void を返す関数は実際には undefined を返します。）

```ts
const myFunction = z
  .function()
  .args(z.string())
  .implement((arg) => {
    return [arg.length];
  });

myFunction; // (arg: string)=>number[]
```

関数スキーマから入力スキーマと出力スキーマを取り出します。

```ts
myFunction.parameters();
// => ZodTuple<[ZodString, ZodNumber]>

myFunction.returnType();
// => ZodBoolean
```

<!-- `z.function()` は２つの引数を受け取ります

* `args: ZodTuple` 最初の引数はタプル (`z.tuple([...])` で作成され、関数への引数のスキーマを定義します。関数が引数を受け取らない場合は、空のタプル (`z.tuple([])`) を渡すことができます。
* `returnType: any Zod schema` ２番目の引数は関数の戻り値の型です。任意の Zod スキーマを指定できます。 -->

## プリプロセス

> Zod は、`.preprocess()` を必要とせずにプリミティブな強制機能をサポートするようになりました。詳細については、[強制のドキュメント](#coercion-for-primitives)を参照してください。

通常、Zod は「解析してから変換する」原則で動作します。Zod は最初に入力を検証し、それを一連の transform 関数に渡します。（変換の詳細については、[.transform ドキュメント](#transform) を参照してください）

しかし、解析が行われる前に入力に何らかの変換を適用したい場合もあります。よくある使用例として、型の強制があります。Zod は、`z.preprocess()` を使用してこれを可能にします。

```ts
const castToString = z.preprocess((val) => String(val), z.string());
```

これは `ZodEffects` インスタンスを返します。`ZodEffects` は、プリプロセス、リファインメント、変換に関連するすべてのロジックを含むラッパークラスです。

## カスタムスキーマ

`z.custom()` を使用すると、任意の TypeScript 型の Zod スキーマを作成できます。これは、テンプレート文字列リテラルなど、Zod がサポートしていない型のスキーマを作成するのに便利です。

```ts
const px = z.custom<`${number}px`>((val) => {
  return typeof val === "string" ? /^\d+px$/.test(val) : false;
});

type px = z.infer<typeof px>; // `${number}px`

px.parse("42px"); // "42px"
px.parse("42vw"); // throws;
```

バリデーション関数を提供しない場合、Zod はどんな値でも許可してしまいます。これは危険があります。

```ts
z.custom<{ arg: string }>(); // performs no validation
```

２番目の引数を渡すことで、エラーメッセージやその他のオプションをカスタマイズできます。このパラメータは、[`.refine`](#refine) の params パラメータと同じように機能します。

```ts
z.custom<...>((val) => ..., "custom error message");
```

## スキーマメソッド

すべての Zod スキーマには特定のメソッドが含まれています。

### `.parse`

`.parse(data: unknown): T`

Zod スキーマを指定すると、`.parse` メソッドを呼び出して `data` が有効かどうかを確認できます。有効であれば、完全な型情報を含む値が返されます。そうでない場合は、エラーがスローされます。

> 重要：`.parse` によって返される値は、渡された変数の _ディープクローン_ です。

```ts
const stringSchema = z.string();

stringSchema.parse("fish"); // => returns "fish"
stringSchema.parse(12); // throws error
```

### `.parseAsync`

`.parseAsync(data:unknown): Promise<T>`

非同期の [refinements](#refine) や [transforms](#transform) （後ほど詳しく説明します）を使用する場合は、`.parseAsync` を使用する必要があります。

```ts
const stringSchema = z.string().refine(async (val) => val.length <= 8);

await stringSchema.parseAsync("hello"); // => returns "hello"
await stringSchema.parseAsync("hello world"); // => throws error
```

### `.safeParse`

`.safeParse(data:unknown): { success: true; data: T; } | { success: false; error: ZodError; }`

バリデーションに失敗した際に Zod がエラーをスローしないようにするには、`.safeParse` を使用します。このメソッドは、パースに成功したデータか、バリデーションの問題に関する詳細情報を含む ZodError インスタンスを含むオブジェクトを返します。

```ts
stringSchema.safeParse(12);
// => { success: false; error: ZodError }

stringSchema.safeParse("billie");
// => { success: true; data: 'billie' }
```

結果は _discriminated union_ なので、非常に便利にエラーを処理できます。

```ts
const result = stringSchema.safeParse("billie");
if (!result.success) {
  // handle error then return
  result.error;
} else {
  // do something
  result.data;
}
```

### `.safeParseAsync`

> `.spa` としてエイリアスされています。

次の例は `safeParse` の非同期バージョンです。

```ts
await stringSchema.safeParseAsync("billie");
```

便宜上、これは `.spa` にエイリアスされています。

```ts
await stringSchema.spa("billie");
```

### `.refine`

`.refine(validator: (data:T)=>any, params?: RefineParams)`

Zod では _refinements_ を経由してカスタムバリデーションロジックを提供しています。（複数の問題の作成やエラーコードのカスタマイズなどの高度な機能については、[`.superRefine`](#superrefine) を参照してください）

Zod は、TypeScript を可能な限り忠実に反映するように設計されています。ただし、TypeScript の型システムでは表現できないような、いわゆる「リファインメント型」が多数あります。たとえば、数値が整数であるかどうかや、文字列が有効な電子メールアドレスであるかどうかをチェックします。

たとえば、`.refine` を使用して、_any_ Zod スキーマのカスタムバリデーションチェックを定義できます。

```ts
const myString = z.string().refine((val) => val.length <= 255, {
  message: "String can't be more than 255 characters",
});
```

> ⚠️ リファインメント関数は例外をスローすべきではありません。代わりに、失敗を通知するために偽の値を返す必要があります。

#### 引数

ご覧のとおり、`.refine` は２つの引数を取ります。

1. 第１引数は、バリデーション関数です。この関数は１つの入力（スキーマの推論型である `T` 型）を受け取り、`any` を返します。真の値はすべてバリデーションに合格します。（zod@1.6.2 より前は、バリデーション関数はブール値を返す必要がありました）
2. 第２引数は、いくつかのオプションを受け入れます。これを使用して、特定のエラー処理動作をカスタマイズできます。

```ts
type RefineParams = {
  // override error message
  message?: string;

  // appended to error path
  path?: (string | number)[];

  // params object you can use to customize message
  // in error map
  params?: object;
};
```

高度なケースでは、第２引数は `RefineParams` を返す関数にすることもできます。

```ts
const longString = z.string().refine(
  (val) => val.length > 10,
  (val) => ({ message: `${val} is not more than 10 characters` })
);
```

#### エラーパスをカスタマイズ

```ts
const passwordForm = z
  .object({
    password: z.string(),
    confirm: z.string(),
  })
  .refine((data) => data.password === data.confirm, {
    message: "Passwords don't match",
    path: ["confirm"], // path of error
  });

passwordForm.parse({ password: "asdf", confirm: "qwer" });
```

`path` パラメータを指定したため、結果として生じるエラーは次のようになります。

```ts
ZodError {
  issues: [{
    "code": "custom",
    "path": [ "confirm" ],
    "message": "Passwords don't match"
  }]
}
```

#### 非同期通信のリファインメント

非同期でリファインメントを行うこともできます。

```ts
const userId = z.string().refine(async (id) => {
  // verify that ID exists in database
  return true;
});
```

> ⚠️ 非同期通信でリファインメントを使用する場合は、`.parseAsync` メソッドを使用してデータを解析する必要があります。そうしないと、Zod はエラーをスローします。

#### トランスフォームとの関係

トランスフォームとリファインメントは、組み合わせるて使用するこも可能です。

```ts
z.string()
  .transform((val) => val.length)
  .refine((val) => val > 25);
```

<!-- `path` が `["confirm"]` に設定されているため、このエラーを「Confirm password」テキストボックスの下に簡単に表示できることに注意してください。

```ts
const allForms = z.object({ passwordForm }).parse({
  passwordForm: {
    password: "asdf",
    confirm: "qwer",
  },
});
```

結果として

```

ZodError {
  issues: [{
    "code": "custom",
    "path": [ "passwordForm", "confirm" ],
    "message": "Passwords don't match"
  }]
}
``` -->

### `.superRefine`

`.refine` メソッドは、実際にはより多機能で（そして冗長な）superRefine メソッドの糖衣構文です。次に例を示します。

```ts
const Strings = z.array(z.string()).superRefine((val, ctx) => {
  if (val.length > 3) {
    ctx.addIssue({
      code: z.ZodIssueCode.too_big,
      maximum: 3,
      type: "array",
      inclusive: true,
      message: "Too many items 😡",
    });
  }

  if (val.length !== new Set(val).size) {
    ctx.addIssue({
      code: z.ZodIssueCode.custom,
      message: `No duplicates allowed.`,
    });
  }
});
```

好きなだけ問題を追加することができます。関数の実行中に `ctx.addIssue` が呼び出されなければ、検証は成功です。

通常、リファインメントでは常に `ZodIssueCode.custom` エラーコードでイシューを作成しますが、`superRefine` を使用すると、任意の `ZodIssueCode` のイシューをスローできます。各イシューコードの詳細については、エラー処理ガイド [ERROR_HANDLING.md](ERROR_HANDLING.md) を参照してください。

#### 早期の中断

デフォルトでは、リファインメントのチェックが失敗した後でも解析は続行されます。たとえば、複数のリファインメントを連鎖させると、それらはすべて実行されます。ただし、後続のリファインメントが実行されないように、早期に中断することが望ましい場合があります。これを実現するには、`ctx.addIssue` に `fatal` フラグを渡し、`z.NEVER` を返します。

```ts
const schema = z.number().superRefine((val, ctx) => {
  if (val < 10) {
    ctx.addIssue({
      code: z.ZodIssueCode.custom,
      message: "should be >= 10",
      fatal: true,
    });

    return z.NEVER;
  }

  if (val !== 12) {
    ctx.addIssue({
      code: z.ZodIssueCode.custom,
      message: "should be twelve",
    });
  }
});
```

#### 型リファインメント

`.refine()` または `.superRefine()` に [型述語](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#using-type-predicates) を提供すると、結果の型は述語の型に絞り込まれます。これは、複数のチェーンされたリファインメントや変換を混在させる場合に役立ちます。

```ts
const schema = z
  .object({
    first: z.string(),
    second: z.number(),
  })
  .nullable()
  .superRefine((arg, ctx): arg is { first: string; second: number } => {
    if (!arg) {
      ctx.addIssue({
        code: z.ZodIssueCode.custom, // customize your issue
        message: "object should exist",
      });
    }

    return z.NEVER; // The return value is not used, but we need to return something to satisfy the typing
  })
  // here, TS knows that arg is not null
  .refine((arg) => arg.first === "bob", "`first` is not `bob`!");
```

> ⚠️ 検証が通るかどうかを示すためにブール値を返すのではなく、`ctx.addIssue()` を **使用する必要があります。** 関数の実行中に `ctx.addIssue` が _呼び出されない_ 場合、検証は合格します。

### `.transform`

解析後にデータを変換するには、`transform` メソッドを使用します。

```ts
const stringToNumber = z.string().transform((val) => val.length);

stringToNumber.parse("string"); // => 6
```

#### 連鎖順序

上記の `stringToNumber` は `ZodEffects` サブクラスのインスタンスであることに注意してください。これは `ZodString` のインスタンスではありません。`ZodString` の組み込みメソッド（例：`.email()`）を使用する場合は、変換の前にそれらのメソッドを適用する必要があります。

```ts
const emailToDomain = z
  .string()
  .email()
  .transform((val) => val.split("@")[1]);

emailToDomain.parse("colinhacks@example.com"); // => example.com
```

#### 変換中の検証

`.transform` メソッドは、値の検証と変換を同時に行うことができます。これは、`transform` と `refine` を連鎖させるよりもシンプルで重複が少ないことが多いです。

`.superRefine` と同様に、transform 関数はバリデーションのイシューを登録するために使用できる `addIssue` メソッドを持つ `ctx` オブジェクトを受け取ります。

```ts
const numberInString = z.string().transform((val, ctx) => {
  const parsed = parseInt(val);
  if (isNaN(parsed)) {
    ctx.addIssue({
      code: z.ZodIssueCode.custom,
      message: "Not a number",
    });

    // これは特別なシンボルで、
    // transform 関数から早期に返されます。
    // `never`型なので
    // 推論される戻り値の型には影響しません。
    return z.NEVER;
  }
  return parsed;
});
```

#### リファインメントとの関係

変換とリファインメントは相互に繰り返すことができます。これらは宣言された順に実行されます。

```ts
const nameToGreeting = z
  .string()
  .transform((val) => val.toUpperCase())
  .refine((val) => val.length > 15)
  .transform((val) => `Hello ${val}`)
  .refine((val) => val.indexOf("!") === -1);
```

#### 非同期変換

変換は非同期にすることもできます。

```ts
const IdToUser = z
  .string()
  .uuid()
  .transform(async (id) => {
    return await getUserById(id);
  });
```

> ⚠️ スキーマに非同期変換が含まれている場合は、.parseAsync() または .safeParseAsync() を使用してデータを解析する必要があります。そうしないと、Zod はエラーをスローします。

### `.default`

トランスフォームを活用して、Zod で「デフォルト値」の概念を実装できます。

```ts
const stringWithDefault = z.string().default("tuna");

stringWithDefault.parse(undefined); // => "tuna"
```

オプションで、デフォルト値を生成する必要があるときに再実行される関数を `.default` に渡すことができます。

```ts
const numberWithRandomDefault = z.number().default(Math.random);

numberWithRandomDefault.parse(undefined); // => 0.4413456736055323
numberWithRandomDefault.parse(undefined); // => 0.1871840107401901
numberWithRandomDefault.parse(undefined); // => 0.7223408162401552
```

概念的には、Zod は次のようにデフォルト値を処理します。

1. 入力が `undefined` の場合、デフォルト値が返されます
2. それ以外の場合、データは基本スキーマを使用して解析されます

### `.describe`

`.describe()` を使用して、結果のスキーマに `description` プロパティを追加します。

```ts
const documentedString = z
  .string()
  .describe("A useful bit of text, if you know what to do with it.");
documentedString.description; // A useful bit of text…
```

これは、[`zod-to-json-schema`](https://github.com/StefanTerdell/zod-to-json-schema) のようなライブラリを使用して、JSON スキーマでフィールドを文書化する場合に便利です。

### `.catch`

`catch()` を使用して、解析エラーが発生した際に返される「キャッチ値」を指定します。

```ts
const numberWithCatch = z.number().catch(42);

numberWithCatch.parse(5); // => 5
numberWithCatch.parse("tuna"); // => 42
```

オプションとして、デフォルト値を生成する必要があるときに再実行される関数を `.catch` に渡すことができます。キャッチしたエラーを含む `ctx` オブジェクトがこの関数に渡されます。

```ts
const numberWithRandomCatch = z.number().catch((ctx) => {
  ctx.error; // the caught ZodError
  return Math.random();
});

numberWithRandomCatch.parse("sup"); // => 0.4413456736055323
numberWithRandomCatch.parse("sup"); // => 0.1871840107401901
numberWithRandomCatch.parse("sup"); // => 0.7223408162401552
```

概念的には、Zod は次のように「キャッチ値」を処理します。

1. データは基本スキーマを使用して解析されます
2. 解析に失敗した際は、「キャッチ値」が返されます

### `.optional`

`.optional` は、スキーマの任意入力許容の値を返す便利なメソッドです。

```ts
const optionalString = z.string().optional(); // string | undefined

// equivalent to
z.optional(z.string());
```

### `.nullable`

`null` を許容するスキーマを返す便利なメソッド。

```ts
const nullableString = z.string().nullable(); // string | null

// equivalent to
z.nullable(z.string());
```

### `.nullish`

「nullish」のスキーマを返す便利なメソッドです。nullish スキーマは、`undefined` と `null` の両方を受け入れます。「nullish」の概念の詳細については、[TypeScript 3.7 リリースノート](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-7.html#nullish-coalescing) を参照してください。

```ts
const nullishString = z.string().nullish(); // string | null | undefined

// equivalent to
z.string().nullable().optional();
```

### `.array`

指定されている型の配列スキーマを返す便利なメソッドです。

```ts
const stringArray = z.string().array(); // string[]

// equivalent to
z.array(z.string());
```

### `.promise`

プロミス型のための便利なメソッドです。

```ts
const stringPromise = z.string().promise(); // Promise<string>

// equivalent to
z.promise(z.string());
```

### `.or`

[ユニオン型](#unions) の便利なメソッドです。

```ts
const stringOrNumber = z.string().or(z.number()); // string | number

// equivalent to
z.union([z.string(), z.number()]);
```

### `.and`

インターセクション型を作成するための便利なメソッド。

```ts
const nameAndAge = z
  .object({ name: z.string() })
  .and(z.object({ age: z.number() })); // { name: string } & { age: number }

// equivalent to
z.intersection(z.object({ name: z.string() }), z.object({ age: z.number() }));
```

### `.brand`

`.brand<T>() => ZodBranded<this, B>`

TypeScript の型システムは構造的であるため、構造的に同等な２つの型は同じものとみなされます。

```ts
type Cat = { name: string };
type Dog = { name: string };

const petCat = (cat: Cat) => {};
const fido: Dog = { name: "fido" };
petCat(fido); // works fine
```

場合によっては、TypeScript の内部で _nomimal typing_ （公称型）をシミュレートすることが望ましいことがあります。たとえば、Zod によってバリデーションされた入力のみを受け付ける関数を記述したい場合があります。これは、_branded types_ （ブランド型）で実現できます。

```ts
const Cat = z.object({ name: z.string() }).brand<"Cat">();
type Cat = z.infer<typeof Cat>;

const petCat = (cat: Cat) => {};

// this works
const simba = Cat.parse({ name: "simba" });
petCat(simba);

// this doesn't
petCat({ name: "fido" });
```

内部的には、これはインターセクション型を使用して推論された型に「ブランド」を付けることによって機能します。このようにして、プレーン/ブランド化されていないデータ構造は、スキーマの推論された型に代入することができなくなります。

```ts
const Cat = z.object({ name: z.string() }).brand<"Cat">();
type Cat = z.infer<typeof Cat>;
// {name: string} & {[symbol]: "Cat"}
```

ブランド型は `.parse` の実行結果に影響を与えないことに注意してください。これは静的のみの構文です。

### `.readonly`

`.readonly() => ZodReadonly<this>`

このメソッドは、基本スキーマを使用して入力を解析し、その結果に `Object.freeze()` を呼び出す `ZodReadonly` スキーマインスタンスを返します。推論された型も `readonly` としてマークされます。

```ts
const schema = z.object({ name: z.string() }).readonly();
type schema = z.infer<typeof schema>;
// Readonly<{name: string}>

const result = schema.parse({ name: "fido" });
result.name = "simba"; // error
```

推論された型は、適切な場合には TypeScript 組み込みの readonly 型を使用します。

```ts
z.array(z.string()).readonly();
// readonly string[]

z.tuple([z.string(), z.number()]).readonly();
// readonly [string, number]

z.map(z.string(), z.date()).readonly();
// ReadonlyMap<string, Date>

z.set(z.string()).readonly();
// ReadonlySet<string>
```

### `.pipe`

スキーマは「パイプライン」としてバリデーションにチェーンさせることができます。`.transform()` の後の結果を簡単に検証するのに役立ちます。

```ts
z.string()
  .transform((val) => val.length)
  .pipe(z.number().min(5));
```

`.pipe()` メソッドは `ZodPipeline` インスタンスを返します。

#### `.pipe()` で `z.coerce` の問題を解決

選択した型変換に適したタイプに入力を制約できます。その後、`.pipe()` を使用して型変換を適用します。

制約のない入力の場合：

```ts
const toDate = z.coerce.date();

// works intuitively
console.log(toDate.safeParse("2023-01-01").success); // true

// might not be what you want
console.log(toDate.safeParse(null).success); // true
```

制約付き入力の場合：

```ts
const datelike = z.union([z.number(), z.string(), z.date()]);
const datelikeToDate = datelike.pipe(z.coerce.date());

// still works intuitively
console.log(datelikeToDate.safeParse("2023-01-01").success); // true

// more likely what you want
console.log(datelikeToDate.safeParse(null).success); // false
```

このテクニックを使用して、キャッチされないエラーをスローする挙動を回避することもできます。

制約のない入力の場合：

```ts
const toBigInt = z.coerce.bigint();

// works intuitively
console.log(toBigInt.safeParse("42")); // true

// probably not what you want
console.log(toBigInt.safeParse(null)); // throws uncaught error
```

制約付き入力の場合：

```ts
const toNumber = z.number().or(z.string()).pipe(z.coerce.number());
const toBigInt = z.bigint().or(toNumber).pipe(z.coerce.bigint());

// still works intuitively
console.log(toBigInt.safeParse("42").success); // true

// error handled by zod, more likely what you want
console.log(toBigInt.safeParse(null).success); // false
```

## ガイドとコンセプト

### 型推論

`z.infer<typeof mySchema>` を使用して、任意のスキーマの TypeScript 型を抽出できます。

```ts
const A = z.string();
type A = z.infer<typeof A>; // string

const u: A = 12; // TypeError
const u: A = "asdf"; // compiles
```

**変換については？**

実際には、各 Zod スキーマは内部的に **２つの** 型（入力と出力）を追跡します。ほとんどのスキーマ（たとえば、`z.string()`）では、これら２つは同じです。ただし、変換を追加すると、これら２つの値が異なる可能性があります。たとえば、`z.string().transform(val => val.length)` には、`string` の入力と `number` の出力があります。

次のように入力型と出力型を個別に抽出できます。

```ts
const stringToNumber = z.string().transform((val) => val.length);

// ⚠️ Important: z.infer returns the OUTPUT type!
type input = z.input<typeof stringToNumber>; // string
type output = z.output<typeof stringToNumber>; // number

// equivalent to z.output!
type inferred = z.infer<typeof stringToNumber>; // number
```

### ジェネリック関数の記述

TypeScript ジェネリックを使用すると、Zod スキーマをパラメータとして受け取る再利用可能な関数を作成できます。これにより、型の安全性と推論を維持しながら、カスタム検証ロジック、スキーマ変換などを作成できます。

Zod スキーマを入力として受け取る関数を書こうとするとき、以下のようなアプローチを取ることがあります。

```ts
function inferSchema<T>(schema: z.ZodType<T>) {
  return schema;
}
```

このアプローチは正しくなく、TypeScript が引数を適切に推測する能力を制限してしまいます。何を渡しても、`schema` の型は `ZodType` のインスタンスになります。

```ts
inferSchema(z.string());
// => ZodType<string>
```

このアプローチでは、入力が実際にどのサブクラスであるか（この場合は `ZodString`）という型情報が失われてしまいます。つまり、`inferSchema` の結果に対して `.min()` などの文字列固有のメソッドを呼び出すことはできません。

より良いアプローチは、推論された型だけではなく、_スキーマ全体_ を推論することです。これは、`z.ZodTypeAny` というユーティリティ型を使用して実行できます。

```ts
function inferSchema<T extends z.ZodTypeAny>(schema: T) {
  return schema;
}

inferSchema(z.string());
// => ZodString
```

> `ZodTypeAny` は `ZodType<any, any, any>` の省略形であり、あらゆる Zod スキーマに一致するほど広範囲な型です。

Result は完全に適切に型付けされ、型システムはスキーマの特定のサブクラスを推論できるようになりました。

#### 推論された型の推論

`z.ZodTypeAny` をスキーマの汎用パラメータとして使用するベストプラクティスに従うと、パースされたデータがスキーマの推論された型ではなく、`any` として型付けされるという問題に出会うかもしれません。

```ts
function parseData<T extends z.ZodTypeAny>(data: unknown, schema: T) {
  return schema.parse(data);
}

parseData("sup", z.string());
// => any
```

TypeScript 推論の仕組みにより、`schema` は推論された型ではなく `ZodTypeAny` のように扱われます。`z.infer` を使用して型キャストすることでこれを修正できます。

```ts
function parseData<T extends z.ZodTypeAny>(data: unknown, schema: T) {
  return schema.parse(data) as z.infer<T>;
  //                        ^^^^^^^^^^^^^^ <- add this
}

parseData("sup", z.string());
// => string
```

#### 許容入力の制限

`ZodType` クラスには３つの汎用パラメータがあります。

```ts
class ZodType<
  Output = any,
  Def extends ZodTypeDef = ZodTypeDef,
  Input = Output
> { ... }
```

ジェネリック入力でこれらを制限することで、関数への入力として許可されるスキーマを制限できます。

```ts
function makeSchemaOptional<T extends z.ZodType<string>>(schema: T) {
  return schema.optional();
}

makeSchemaOptional(z.string());
// works fine

makeSchemaOptional(z.number());
// Error: 'ZodNumber' is not assignable to parameter of type 'ZodType<string, ZodTypeDef, string>'
```

### エラー処理

Zod は、`ZodError` と呼ばれる Error のサブクラスを提供します。ZodErrors には、検証の問題に関する詳細な情報を含む `issues` 配列が含まれています。

```ts
const result = z
  .object({
    name: z.string(),
  })
  .safeParse({ name: 12 });

if (!result.success) {
  result.error.issues;
  /* [
      {
        "code": "invalid_type",
        "expected": "string",
        "received": "number",
        "path": [ "name" ],
        "message": "Expected string, received number"
      }
  ] */
}
```

> 考えられるエラーコードとエラーメッセージのカスタマイズ方法の詳細については、専用のエラー処理ガイドをご覧ください。[ERROR_HANDLING.md](ERROR_HANDLING.md)

Zod のエラー報告では、_完全性_ と _正確性_ を重視しています。エンドユーザーに有用なエラーメッセージを提示したい場合は、エラーマップ（エラー処理ガイドで詳しく説明）を使用して Zod のエラーメッセージを上書きするか、[`zod-validation-error`](https://github.com/causaly/zod-validation-error) などのサードパーティライブラリを使用する必要があります。

### エラーのフォーマット

`.format()` メソッドを使用して、以下のエラーをネストされたオブジェクトに変換することができます。

```ts
const result = z
  .object({
    name: z.string(),
  })
  .safeParse({ name: 12 });

if (!result.success) {
  const formatted = result.error.format();
  /* {
    name: { _errors: [ 'Expected string, received number' ] }
  } */

  formatted.name?._errors;
  // => ["Expected string, received number"]
}
```

## 比較

広く使用されているバリデーションライブラリは他にもいくつかありますが、それらはすべて、理想的な開発者エクスペリエンスとは言えない設計上の制限があります。

<!-- The table below summarizes the feature differences. Below the table there are more involved discussions of certain alternatives, where necessary. -->

<!-- | Feature                                                                                                                | [Zod](https://github.com/colinhacks) | [Joi](https://github.com/hapijs/joi) | [Yup](https://github.com/jquense/yup) | [io-ts](https://github.com/gcanti/io-ts) | [Runtypes](https://github.com/pelotom/runtypes) | [ow](https://github.com/sindresorhus/ow) | [class-validator](https://github.com/typestack/class-validator) |
| ---------------------------------------------------------------------------------------------------------------------- | :-----------------------------: | :----------------------------------: | :-----------------------------------: | :--------------------------------------: | :---------------------------------------------: | :--------------------------------------: | :-------------------------------------------------------------: |
| <abbr title='Any ability to extract a TypeScript type from a validator instance counts.'>Type inference</abbr>         |               🟢                |                  🔴                  |                  🟢                   |                    🟢                    |                       🟢                        |                    🟢                    |                               🟢                                |
| <abbr title="Yup's inferred types are incorrect in certain cases, see discussion below.">Correct type inference</abbr> |               🟢                |                  🔴                  |                  🔴                   |                    🟢                    |                       🟢                        |                    🟢                    |                               🟢                                |

<abbr title="number, string, boolean, null, undefined">Primitive Types</abbr>
<abbr title="Includes any checks beyond 'Is this a string?', e.g. min/max length, isEmail, isURL, case checking, etc.">String Validation</abbr>
<abbr title="Includes any checks beyond 'Is this a number?', e.g. min/max, isPositive, integer vs float, etc.">Number Validation</abbr>
Dates

Primitive Literals
Object Literals
Tuple Literals
Objects
Arrays
Non-empty arrays
Unions
Optionals
Nullable
Enums
Enum Autocomplete
Intersections
Object Merging
Tuples
Recursive Types
Function Schemas

<abbr title="For instance, Yup allows custom error messages with the syntax yup.number().min(5, 'Number must be more than 5!')">Validation Messages</abbr>
Immutable instances
Type Guards
Validity Checking
Casting
Default Values
Rich Errors
Branded -->

<!-- - Missing object methods: (pick, omit, partial, deepPartial, merge, extend)

* Missing nonempty arrays with proper typing (`[T, ...T[]]`)
* Missing lazy/recursive types
* Missing promise schemas
* Missing function schemas
* Missing union & intersection schemas
* Missing support for parsing cyclical data (maybe)
* Missing error customization -->

### Joi

[https://github.com/hapijs/joi](https://github.com/hapijs/joi)

静的型推論をサポートしていません 😕

### Yup

[https://github.com/jquense/yup](https://github.com/jquense/yup)

Yup は、最初は vanilla JS で実装され、後に TypeScript で書き直されたフル機能のライブラリです。

- キャストとトランスフォームをサポート
- すべてのオブジェクトフィールドはデフォルトでオプションです
<!-- - 適切な型付けの空でない配列がありません (`[T, ...T[]]`) -->
- プロミススキーマが欠落している
- 関数スキーマが欠落している
- 論理和と論理積のスキーマが欠落している

<!-- ¹Yup has a strange interpretation of the word `required`. Instead of meaning "not undefined", Yup uses it to mean "not empty". So `yup.string().required()` will not accept an empty string, and `yup.array(yup.string()).required()` will not accept an empty array. Instead, Yup us Zod arrays there is a dedicated `.nonempty()` method to indicate this, or you can implement it with a custom refinement. -->

### io-ts

[https://github.com/gcanti/io-ts](https://github.com/gcanti/io-ts)

io-ts は gcanti による優れたライブラリです。io-ts の API は Zod の設計に多大な影響を与えました。

私たちの経験では、io-ts は多くの場合、開発者の経験よりも関数型プログラミングの純粋さを優先します。これは有効で立派な設計目標ですが、io-ts を、より手続き型またはオブジェクト指向のバイアスを持つ既存のコードベースに統合することが特に難しくなります。たとえば、io-ts でオプションのプロパティを持つオブジェクトを定義する方法を考えてみましょう。

```ts
import * as t from "io-ts";

const A = t.type({
  foo: t.string,
});

const B = t.partial({
  bar: t.number,
});

const C = t.intersection([A, B]);

type C = t.TypeOf<typeof C>;
// returns { foo: string; bar?: number | undefined }
```

必須プロパティとオプションプロパティを別々のオブジェクト バリデーターで定義し、オプションプロパティを `t.partial`（すべてのプロパティをオプションとしてマークする）に渡してから、それらを `t.intersection` と組み合わせる必要があります。

Zod での同等の例を考えてみましょう。

```ts
const C = z.object({
  foo: z.string(),
  bar: z.number().optional(),
});

type C = z.infer<typeof C>;
// returns { foo: string; bar?: number | undefined }
```

このより宣言的な API により、スキーマ定義が大幅に簡潔になります。

`io-ts` では、結果を解析してエラーを処理するために、gcanti の関数型プログラミング ライブラリ `fp-ts` も必要です。これは、コードベースを厳密に機能的なものにしたい開発者にとって、もう 1 つの素晴らしいリソースです。ただし、`fp-ts` に依存すると、必然的に多くの知的オーバーヘッドが発生します。開発者は、ライブラリを使用するために、関数型プログラミングの概念と `fp-ts` の命名法に精通している必要があります。

- シリアル化とデシリアル化の変換を備えたコーデックをサポート
- ブランドタイプをサポート
- 高度な関数型プログラミング、高階型、`fp-ts` 互換性をサポート
- 不足しているオブジェクト メソッド: (pick、omit、partial、deepPartial、merge、extend)
- 適切な型付けの空でない配列が見つかりません (`[T, ...T[]]`)
- プロミススキーマが欠落している
- 関数スキーマが欠落している

### Runtypes

[https://github.com/pelotom/runtypes](https://github.com/pelotom/runtypes)

優れた型推論サポート。

- 「パターンマッチング」をサポート：ユニオンに分配される計算プロパティ
- 不足しているオブジェクトメソッド： (deepPartial、merge)
- 適切な型付けの空でない配列が見つかりません（`[T, ...T[]]`）
- プロミススキーマが欠落している
- エラーのカスタマイズが不足しています

### Ow

[https://github.com/sindresorhus/ow](https://github.com/sindresorhus/ow)

Ow は関数の入力検証に特化しています。これは複雑なアサートステートメントを簡単に表現できるライブラリですが、型指定されていないデータを解析することはできません。サポートされる型ははるかに多岐にわたります。Zod は TypeScript の型システムとほぼ１対１でマッピングしますが、ow ではすぐに使用できる非常に特殊な複数の型を検証できます）例：`int32Array`、README の完全なリストを参照）。

関数の入力を検証したい場合は、Zod の関数スキーマを使用してください。これは、関数の型宣言を繰り返すことなく再利用できる、はるかにシンプルなアプローチです（すべての関数の先頭に多くの ow アサーションをコピーペーストすることです）。また、Zod では戻り値の型も検証できるため、下流に予期しないデータが渡されないことを確認できます。

## 更新履歴

更新履歴は [CHANGELOG.md](CHANGELOG.md) をご覧ください。
