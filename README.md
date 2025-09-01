# minimal-reproduction-template

First, read the [Renovate minimal reproduction instructions](https://github.com/renovatebot/renovate/blob/main/docs/development/minimal-reproductions.md).

Then replace the current `h1` with the Renovate Issue/Discussion number.

## Current behavior

Only the `dependencyManagement` section is updated with relocation.

```xml
	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>org.apache.commons</groupId>
				<artifactId>commons-io</artifactId>
				<version>1.3.2</version>
			</dependency>
		</dependencies>
	</dependencyManagement>
```

is migrated to

```xml
	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>commons-io</groupId>
				<artifactId>commons-io</artifactId>
				<version>1.3.2</version>
			</dependency>
		</dependencies>
	</dependencyManagement>
```

(this is correct)

However, the below usage of the dependency *also* needs to be updated.

## Expected behavior

The below part

```xml
        <dependency>
            <dependency>
				<groupId>org.apache.commons</groupId>
				<artifactId>commons-io</artifactId>
			</dependency>
        </dependency>
```

Should be updated to

```xml
        <dependency>
            <dependency>
				<groupId>commons-io</groupId>
				<artifactId>commons-io</artifactId>
			</dependency>
        </dependency>
```

as part of the same change as the above update.

## Link to the Renovate issue or Discussion

Put your link to the Renovate issue or Discussion here.
