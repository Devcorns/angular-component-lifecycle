# angular-component-lifecycle
This tutorial to better understand the lifecycle hook of component

## ngOnChanges lifecycle hook 	
- ngOnChanges() **`works first`** in angular compomonent life cycle
- it fires **before ngOnInit()** :ok_hand:	 lifecycle hooks
- **it only works when parent data changes and passes to child** :point_left:		
- **it will not works when child data changes**
- it will only **works** with **@Input()** decorator
  - **@Input() Decorator** works when data passes from parent component


```

**`Parent component like (parent.html)`**
<p>Parent html file passing data to child component</p>
<app-child-component [parentData]=data></app-child-component>

```

