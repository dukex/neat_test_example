# NEAT TEST EXAMPLE

My test.scss:

```scss
@import 'bourbon/bourbon';
@import 'neat';

.omega-default{  @include omega; }
.omega-table{  @include omega(table); }
.omega-default-left{  @include omega(block, left); }
.omega-table-left{  @include omega(table, left); }

.omega-nth-default{ @include omega(4n) }

.omega-nth-table{  @include omega(4n, table); }
.omega-nth-default-left{  @include omega(4n, block, left); }
.omega-nth-table-left{  @include omega(4n, table, left); }
```

run:
```shell
$ rake "test[../neat/app/assets/stylesheets/test.scss, ../neat/app/assets/stylesheets/bourbon/lib/bourbon.rb]"
```
