# grpc-plain-text-quickstart-ver3

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: <https://quarkus.io/>.

# このプロジェクトの作成方法

`quarkus create app org.acme:grpc-plain-text-quickstart-ver3 --kotlin --gradle`

# 手順

1. `build.gradle` に`implementation 'io.quarkus:quarkus-grpc'`を追加

2. `src/main/proto` ディレクトリを作成し、`helloworld.proto` を作成

3. `./gradlew compileKotlin`によりコードを生成 

- 生成先は`build/classes`以下のjavaファイル

- このファイルを使ってKotlinで実装する！

- 生成されるファイルイメージは[こちら](https://ja.quarkus.io/guides/grpc-getting-started#configuring-your-project)

4. gRPCサービスの実装

- 注意点は、「`Greeter`」を実装すること、実装するクラスに`@GrpcService`を付与すること（これがないとgrpcサービスが使えない）

5. `application.properties`に`quarkus.grpc.clients.hello.host=localhost`を追加

6. `./gradlew quarkusDev`で起動
 
- 今回検証できるエンドポイントはこちら

- http://localhost:8080/hello

- http://localhost:8080/hello/quarkus

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:

```shell script
./gradlew quarkusDev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at <http://localhost:8080/q/dev/>.

## Packaging and running the application

The application can be packaged using:

```shell script
./gradlew build
```

It produces the `quarkus-run.jar` file in the `build/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `build/quarkus-app/lib/` directory.

The application is now runnable using `java -jar build/quarkus-app/quarkus-run.jar`.

If you want to build an _über-jar_, execute the following command:

```shell script
./gradlew build -Dquarkus.package.jar.type=uber-jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar build/*-runner.jar`.

## Creating a native executable

You can create a native executable using:

```shell script
./gradlew build -Dquarkus.native.enabled=true
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using:

```shell script
./gradlew build -Dquarkus.native.enabled=true -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./build/grpc-plain-text-quickstart-ver3-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult <https://quarkus.io/guides/gradle-tooling>.

## Related Guides

- Kotlin ([guide](https://quarkus.io/guides/kotlin)): Write your services in Kotlin

## Provided Code

### REST

Easily start your REST Web Services

[Related guide section...](https://quarkus.io/guides/getting-started-reactive#reactive-jax-rs-resources)
