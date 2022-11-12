# angular-component-lifecycle
This tutorial to better understand the lifecycle hook of component

## ngOnChanges lifecycle hook
- ngOnChanges() **works first** in angular compomonent life cycle
- it fires **before ngOnInit()** lifecycle hooks
- **it works when parent data changes and passes to child**
- **it will not works when child data changes**
- it will only **works** with **@Input()** decorator
  - **@Input() Decorator** works when data comes from parent component



