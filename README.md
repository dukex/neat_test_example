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

output:
```
passed, .omega-default has margin-right equal 0

passed, .omega-table has padding-right equal 0

passed, .omega-default-left has margin-left equal 0

passed, .omega-table-left has padding-left equal 0

passed, .omega-nth-default:nth-child(4n) has margin-right equal 0

passed, .omega-nth-table:nth-child(4n) has padding-right equal 0

passed, .omega-nth-default-left:nth-child(4n) has margin-left equal 0

passed, .omega-nth-table-left:nth-child(4n) has padding-left equal 0
```
