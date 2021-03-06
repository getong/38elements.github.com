---
layout: posts
title: Marionette.jsのRegionメモ
---
[document](http://marionettejs.com/docs/master/marionette.region.html)  

RegionはApplicationとViewで子Viewを配置する要素を登録する。

Viewでは以下のように設定する。

```
   regions: {
        <region name>: '<selector>',
        ...
    }
```
<br>

#### Region要素とView要素の置換
以下のようにするとid=fooの要素をViewの要素に置き換えることができる。

```
'regions': {
    'region1': {
        'el': '#foo',
        'replaceElement': true
    }
}
```
<br>

#### 動的な設定

以下のように動的に設定することができる。

```
'regions': function(options) { 
   return {
      'region1': {
         'el': '#foo',
         'replaceElement': true
      }
   };
}
```
<br>

#### 動的な追加

```
view.addRegion(region_name, selector);
```
<br>

#### Viewの配置と削除

* region.empty()  
ビューの削除

* region.show(view, options)  
optionsに{preventDestroy: true}を指定した場合、既存のViewは削除されない

* region.hasView()  
regionにviewが存在しているか  

* どのように子ViewがRegionに配置されるか [\*](http://marionettejs.com/docs/master/marionette.region.html#set-how-views-el-is-attached)

<br>
<hr>
[Marionette.jsメモ](/2016/09/11/backbone_marionette.html)  
[handlebars.js](http://handlebarsjs.com/reference.html)  
[Backbone.js](http://backbonejs.org/#View)  
