**replaceSlotDisplay 通过名字修改 slot**

```typescript
let factory = dragonBones.CCFactory.getInstance() as any;
factory.replaceSlotDisplay(this.replaceArmatureDisplay!.getArmatureKey(), replaceArmatureName , "weapon_r", displayName, slot);
```

**通过index改变slot**

```typescript
this._armatureComponent.armature.getSlot("weapon_hand_l").displayIndex = this._leftWeaponIndex;
```

**整个替换Tex**

```typescript
const factory = dragonBones.CocosFactory.factory;

const resources = [
	cc.url.raw("resources/you_xin/body/body_ske.json"),
	cc.url.raw("resources/you_xin/body/body_tex.json"),
	cc.url.raw("resources/you_xin/body/body_tex.png"),
];

this._suitConfigs.push([
	"20106010",
	"20106010_1",
	"20208006",
]);

factory.parseDragonBonesData(cc.loader.getRes(resources[0]));
factory.parseTextureAtlasData(cc.loader.getRes(resources[1]), cc.loader.getRes(resources[2]));

//part: this._suitConfigs[0]
const partArmatureData = factory.getArmatureData(part);
factory.replaceSkin(this._armatureComponent.armature, partArmatureData.defaultSkin);
```

**其他可能性**

```typescript
BaseFactory.ts
/**
* - 获取特定的骨架数据。
* @param name - 骨架数据名称。
* @param dragonBonesName - DragonBonesData 实例的缓存名称。
* @see dragonBones.ArmatureData
* @version DragonBones 5.1
* @language zh_CN
*/
getArmatureData(name: string, dragonBonesName?: string): ArmatureData | null;
```

```typescript
ArmatureData.ts
/**
* - 获取特定皮肤数据。
* @param name - 皮肤名称。
* @version DragonBones 3.0
* @language zh_CN
*/
getSkin(name: string): SkinData | null;
```

```typescript
SkinData.ts
getDisplay(slotName: string, displayName: string): DisplayData | null;
```

```typescript
Slot.ts
slot.replaceDisplayData(displayData);
```

```
dragonBones.ArmatureDisplay.ts
armatureDisplay.armature();
```

