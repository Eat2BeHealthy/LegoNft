
修订日期：2022-4-20

**Loot Lego NFT**

*Satoshi invites you to eat pizza.*

*中本聪请你吃pizza。*



**1、Nft 可组合、可拆卸。就像 pizza 可以由各种佐料组合。**

**2、Mint 该nft时，探索用户钱包虚拟币。每个虚拟币就是一种佐料。不用考虑币是盐还是其他啥，币就是币。**

生成nft时把该地址下所有币都添加进去。

在pizza的svg图里显示这些币。

**3、有总量限制，例如1万个。**

**4、有时间限制，在 pizza day 前后48小时内mint。**

（要考虑世界时间，美国时间5月21日0:00 ~ 5月22日0:00。对应北京时间：5月22日12:00 ~ 5月23日12:00）

需要确认中美时差。上述时间按-12小时算，是美国夏令时。不算夏令时中美时差是-13，即北京时间是13:00。

**5、mint 的用户需要拥有 loot、more loot 或 poa 代币。**

（另外一个方案是：mint时先由 loot、more loot、poa用户先mint，第二天如果还有剩余，其他人再mint）

**6、该 NFT 是未来我们 eat 2 earn（或说 eat to be health）项目的治理加权代币。拥有该nft的人，获得一定治理币加权。**

**7、该 nft 对治理加权的方案是：如果长期持有，随着时间推移它会进化（3664的 Evolvable 功能）。相当于拥有更多加权。**

每一次转手，都会降低加权。例如每次转手降低 1/2 。起始加权是1.长期持有会超过1.每次转手降低1/2。但最低不会低于1.

---
修订日期：2022-4-26

## eip 3664
特点：继承自 eip1155。在1155的物品id后面，增加属性id概念。如图：
| 物品 | 属性 |
|--|--|
| 1 | 1 |
| 1 | 2 |
| 1 | 3 |
| **2** | **1** |
| **2** | **2** |
| **...** | **...** |

针对每个属性，它提供统一的几大功能：

 1. 某个物品->属性，可以转移给另一个物品。
 2. 某个物品->属性，可以升级。3664约定了2个内部属性：属性当前level，最大level。
 3. 某个物品->属性，可以进化。进化可以限定时间，必须超过一定时间才能进化（实际是用区块数目代替时间）。3664提供1个内部属性：进化成功率。运气不好就会进化失败，物品或属性就会损坏。损坏之后的物品无法使用，需要用3664约定的repair函数去“修复”。进化的目标内容，是该属性的 level。这点完全等同于升级。
 
 进化和升级，都是对应 level 做变化。如果要简单，就用升级功能。要复杂的玩法例如时间限制、失败概率、修复等等，就用进化。
 
---
## eip2569
特点：提供 svg 图片“**动态生成**”功能。且已获得钱包广泛支持。是去中心化的。
缺点：该协议只能对物品动态生成 svg，无法对“物品->属性”提供图片。

---
**乐高Nft玩法设想：**
 - 采用 3664 + 2569。
 - 采用3664里的可进化玩法（不用可升级玩法，区别见上）。
 - 随着时间推进，level 增加。level代表我们的投票治理权。
 - 一个pizza nft相当于一个物品。它里面包含若干子属性：
	
	- 等级。（用于进化、用于治理权）
	- 代币数目。可转移。
		完整 pizza 是100%。必须由**1万**种不同代币才能成为满pizza。以纪念1万枚比特币。
		当不足100%时显示svg是**一片**pizza。如图：
		![一片pizza](https://media1.thehungryjpeg.com/thumbs2/800_3492505_22d99419e3ed48a48016e1f1f8449b24f45df396_pizza-clip-art-fast-food-svg-food-files.jpg)
		大家买来组合，直到1万种代币，才可成为完整pizza。
	- *（其他可拆卸属性玩法待定，还没想到）*
	 
- 一个pizza  nft本身包含一些特殊信息。属于整个 nft 全局所有。不可转移、不可拆分。
	- 代币（mint瞬间钱包里的代币地址、代币名称、代币数量）。
	 - 一句话（10个字以内）。
	 - 整个pizza 的svg图。 **<-- 需要大雄老师找美工设计10个pizza矢量图给我**

