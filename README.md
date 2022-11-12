# angular-component-lifecycle
This tutorial to better understand the lifecycle hook of component

## 1- ngOnChanges lifecycle hook 	
- ngOnChanges() **`works first`** in angular compomonent life cycle
- it fires **before ngOnInit()** :ok_hand:	 lifecycle hooks
- **it only works when parent data changes and passes to child** :point_left:		
- **it will not works when child data changes**
- it will only **works** with **@Input()** decorator
  - **@Input() Decorator** works when data passes from parent component

```
Parent controller like (parent.component.ts)

data = "this is parent data for child component";

updateData() {
  if(this.data.length) {
    this.data = ""
  } else {
    this.data = "new data from parent";   
  }
}

```

```
Parent view like (parent.html)

<p>Parent html file passing data to child component</p>
<button (click)="updateData()">Update parent data</button>
<app-child-component [parentData]=data></app-child-component>

```

```
child controller like (child.component.ts)

@Input() parentData:string = "";
  
  ngOnInit() {
    console.log(this.parentData)
  }
  ngOnChanges(changes: SimpleChanges) {
    console.log("from ng on change hook, ",this.parentData);
    console.log("changes parameters",changes['parentData'].currentValue)
    if(changes['parentData'].currentValue == "") {
      console.log("values empty")
    }
  }
```

