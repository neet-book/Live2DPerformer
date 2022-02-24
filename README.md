# Live2DPerformerd
基于CubismSDK的live2d库， 用于快速在页面中展示你的live2D模型，并进行交互



## 使例

```javascript
import Live2DPerformer from 'live2dperformer'

const draw = Document.createElement('canvas')
const live2dPerformer = new Live2DPerformer(draw)

live2dPerformer.loadModel('Hiyori', '/Hiyori.model3.json')

const modle = live2dPerformer.models.Hiyori

model.startMotion(modle.groupMotions.get('TapBody')[0])
model.startExpressions(model.expressions[0])

model.on("click", (event) => {
  	  const { pointX, pointY } = event.info
      console.log(`点击位置[${pointX}, ${pointY}`)
})

model.onHit('body', (event) => {
    const motion = model.groupMotions.get('TapBody')[0]
    model.startMotion(motion)
})
```

