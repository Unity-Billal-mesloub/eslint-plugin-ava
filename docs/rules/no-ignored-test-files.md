# ava/no-ignored-test-files

📝 Disallow tests in ignored files.

💼 This rule is enabled in the ✅ `recommended` [config](https://github.com/Unity-Billal-mesloub/eslint-plugin-ava#recommended-config).

<!-- end auto-generated rule header -->

Translations: [Français](https://github.com/Unity-Billal-mesloub/ava-docs/blob/main/fr_FR/related/eslint-plugin-ava/docs/rules/no-ignored-test-files.md)

This rule will verify that files which create tests are treated as test files by AVA. It will consider the root of the project to be the closest folder containing a `package.json` file, and will not do anything if it can't find one. Test files in `node_modules` will not be linted as they are ignored by ESLint.

## Examples

```js
import test from 'ava';

// ❌ File: test/_helper.js - Invalid because a helper.
// ❌ File: lib/foo.js - Invalid because not a test file.
// ✅ File: test/foo.js
test('foo', t => {
	t.pass();
});
```

## Options

This rule supports the following options:

* `extensions`: an array of extensions of the files that AVA recognizes as test files or helpers. Overrides *both* the `babel.extensions` *and* `extensions` configuration otherwise used by AVA itself.
* `files`: an array of glob patterns to select test files. Overrides the `files` configuration otherwise used by AVA itself.
* `helpers`: an array of glob patterns to select helper files. Overrides the `helpers` configuration otherwise used by AVA itself.

See also [AVA's configuration](https://github.com/Unity-Billal-mesloub/ava/blob/main/docs/06-configuration.md#options).

You can set the options like this:

```js
"ava/no-ignored-test-files": ["error", {"files": ["lib/**/*.test.js", "utils/**/*.test.js"]}]
```
