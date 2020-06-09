> awesome-task-runner v0.0.3

### Table of Contents

- [RunnerOptions][1]
- [constructor][2]
  - [Parameters][3]
- [set][4]
  - [Parameters][5]
- [get][6]
  - [Parameters][7]
- [clear][8]
- [task][9]
  - [Parameters][10]
- [run][11]
  - [Parameters][12]
- [TaskDoneFn][13]
- [TaskFn][14]
  - [Parameters][15]
- [TasksDoneFn][16]
  - [Parameters][17]

## RunnerOptions

Runner options.

Type: [Object][18]

## constructor

Creates an instance of Runner.

```js
const runner = new Runner();
```

### Parameters

- `options` **[RunnerOptions][19]** (optional, default `{}`)

## set

Merges the internal `data` object of runner with provided `data` object

```js
runner.set({ foo: "bar" });
```

### Parameters

- `key` **([string][20] \| [object][18])**
- `value` **any?**

## get

Get value from runner's data object

```js
runner.get("foo");
```

### Parameters

- `key` **[string][20]**

Returns **any**

## clear

Clear runner's data

```js
runner.clear();
```

## task

Register tasks to run later

```js
runner.task("foo", (done) => {
  console.log("foo doing stuff");
  done();
});
```

### Parameters

- `taskName` **[string][20]**
- `fn` **[TaskFn][21]** function to invoke when the task runs

## run

Runs the registered tasks provided in `tasks` argument.

```js
runner.run("foo", (err) => {
  if (err) throw err;
});
```

### Parameters

- `tasks` **([String][20] \| [Array][22]&lt;[String][20]>)** string or array of strings.
- `cb` **[TasksDoneFn][23]** A callback function, will be invoked once the runner has finished all the tasks.

## TaskDoneFn

Task Done Function.

Type: [Function][24]

## TaskFn

Task Function.

Type: [Function][24]

### Parameters

- `fn` **[TaskDoneFn][25]** A callback function. When invoked, tells the runner that the this task is finished.

## TasksDoneFn

Type: [Function][24]

### Parameters

- `err` **[Error][26]?**

[1]: #runneroptions
[2]: #constructor
[3]: #parameters
[4]: #set
[5]: #parameters-1
[6]: #get
[7]: #parameters-2
[8]: #clear
[9]: #task
[10]: #parameters-3
[11]: #run
[12]: #parameters-4
[13]: #taskdonefn
[14]: #taskfn
[15]: #parameters-5
[16]: #tasksdonefn
[17]: #parameters-6
[18]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object
[19]: #runneroptions
[20]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String
[21]: #taskfn
[22]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array
[23]: #tasksdonefn
[24]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function
[25]: #taskdonefn
[26]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Error