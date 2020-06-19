<template>
  <div class="container">
    <client-only>
      <i class="fa fa-user-circle" aria-hidden="true"></i>

      <TextRenderer
        v-for="(font, i) in useFontList"
        :key="i"
        :family="font.family"
        :weight="font.weight"
      >
        吾輩わがはいは猫である。名前はまだ無い。
        どこで生れたかとんと見当けんとうがつかぬ。何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれは書生という人間中で一番獰悪どうあくな種族であったそうだ。この書生というのは時々我々を捕つかまえて煮にて食うという話である。しかしその当時は何という考もなかったから別段恐しいとも思わなかった。ただ彼の掌てのひらに載せられてスーと持ち上げられた時何だかフワフワした感じがあったばかりである。掌の上で少し落ちついて書生の顔を見たのがいわゆる人間というものの見始みはじめであろう。この時妙なものだと思った感じが今でも残っている。第一毛をもって装飾されべきはずの顔がつるつるしてまるで薬缶やかんだ。その後ご猫にもだいぶ逢あったがこんな片輪かたわには一度も出会でくわした事がない。のみならず顔の真中があまりに突起している。そうしてその穴の中から時々ぷうぷうと煙けむりを吹く。どうも咽むせぽくて実に弱った。これが人間の飲む煙草たばこというものである事はようやくこの頃知った。
        この書生の掌の裏うちでしばらくはよい心持に坐っておったが、しばらくすると非常な速力で運転し始めた。書生が動くのか自分だけが動くのか分らないが無暗むやみに眼が廻る。胸が悪くなる。到底とうてい助からないと思っていると、どさりと音がして眼から火が出た。それまでは記憶しているがあとは何の事やらいくら考え出そうとしても分らない。
        ふと気が付いて見ると書生はいない。たくさんおった兄弟が一疋ぴきも見えぬ。肝心かんじんの母親さえ姿を隠してしまった。その上今いままでの所とは違って無暗むやみに明るい。眼を明いていられぬくらいだ。はてな何でも容子ようすがおかしいと、のそのそ這はい出して見ると非常に痛い。吾輩は藁わらの上から急に笹原の中へ棄てられたのである。
        ようやくの思いで笹原を這い出すと向うに大きな池がある。吾輩は池の前に坐ってどうしたらよかろうと考えて見た。別にこれという分別ふんべつも出ない。しばらくして泣いたら書生がまた迎に来てくれるかと考え付いた。ニャー、ニャーと試みにやって見たが誰も来ない。そのうち池の上をさらさらと風が渡って日が暮れかかる。腹が非常に減って来た。泣きたくても声が出ない。仕方がない、何でもよいから食物くいもののある所まであるこうと決心をしてそろりそろりと池を左ひだりに廻り始めた。どうも非常に苦しい。そこを我慢して無理やりに這はって行くとようやくの事で何となく人間臭い所へ出た。ここへ這入はいったら、どうにかなると思って竹垣の崩くずれた穴から、とある邸内にもぐり込んだ。縁は不思議なもので、もしこの竹垣が破れていなかったなら、吾輩はついに路傍ろぼうに餓死がししたかも知れんのである。一樹の蔭とはよく云いったものだ。この垣根の穴は今日こんにちに至るまで吾輩が隣家となりの三毛を訪問する時の通路になっている。さて邸やしきへは忍び込んだもののこれから先どうして善いいか分らない。そのうちに暗くなる、腹は減る、寒さは寒し、雨が降って来るという始末でもう一刻の猶予ゆうよが出来なくなった。仕方がないからとにかく明るくて暖かそうな方へ方へとあるいて行く。今から考えるとその時はすでに家の内に這入っておったのだ。ここで吾輩は彼かの書生以外の人間を再び見るべき機会に遭遇そうぐうしたのである。第一に逢ったのがおさんである。これは前の書生より一層乱暴な方で吾輩を見るや否やいきなり頸筋くびすじをつかんで表へ抛ほうり出した。いやこれは駄目だと思ったから眼をねぶって運を天に任せていた。しかしひもじいのと寒いのにはどうしても我慢が出来ん。吾輩は再びおさんの
      </TextRenderer>
    </client-only>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import TextRenderer from '@/components/TextRenderer.vue'
// import webfonts from '@/assets/webfonts.json'

// const googleFontLink = ()
function getFontParam(family: string, variants: string[]): string {
  return `${family}:${variants
    .map((variant) => {
      return variant
        .replace(/italic/, 'i')
        .replace(/regular/, '400')
        .replace(/^i$/, '400i')
    })
    .join(',')}`
}
export default Vue.extend({
  components: {
    TextRenderer
  },
  data() {
    return {
      useFontList: [
        // {
        //   family: 'Montserrat',
        //   weight: '200'
        // },
        // {
        //   family: 'Metal Mania',
        //   weight: '400'
        // },
        {
          family: 'Kosugi',
          weight: '400'
        },
        {
          family: 'Roboto',
          weight: '900i'
        },
        {
          family: 'Noto Sans JP',
          weight: '100'
        },
        {
          family: 'Noto Sans JP',
          weight: '300'
        },
        {
          family: 'Noto Sans JP',
          weight: '400'
        },
        {
          family: 'Noto Sans JP',
          weight: '500'
        },
        {
          family: 'Noto Sans JP',
          weight: '700'
        },
        {
          family: 'Noto Sans JP',
          weight: '900'
        },
        {
          family: 'Noto Serif JP',
          weight: '100'
        },
        {
          family: 'Noto Serif JP',
          weight: '300'
        },
        {
          family: 'Noto Serif JP',
          weight: '400'
        },
        {
          family: 'Noto Serif JP',
          weight: '500'
        },
        {
          family: 'Noto Serif JP',
          weight: '700'
        },
        {
          family: 'Noto Serif JP',
          weight: '900'
        }
      ],
      useOnly: true
    }
  },
  computed: {
    fontParams(): string[] {
      if (this.useOnly) {
        return this.useFontList.map((font) => {
          return getFontParam(
            font.family,
            [font.weight]
            //  ['100,300,400,500,700,900']
          ) //, )
        })
      }
      return []

      // return webfonts.items
      //   .filter((item) => item.subsets.includes('japanese'))
      //   .map((item) => {
      //     const { family, variants } = item
      //     return getFontParam(family, variants)
      //   })
    },
    fontLinkList(): string[] {
      // return this.fontParams

      return this.fontParams.reduce((acc: string[], param) => {
        if (acc.length === 0) {
          acc.push(param)
        } else {
          const last = acc[acc.length - 1] || ''
          if (last.length > 5000) {
            acc.push(param)
          } else {
            acc[acc.length - 1] += `|${param}`
          }
        }
        return acc
      }, [])
    }
  },
  head(): {} {
    console.log(this.fontLinkList)

    return {
      title: 'title',
      link: [
        ...this.fontLinkList.map((item) => {
          return {
            // hid: 'googleFonts',
            // rel: 'preload',
            // onload: "this.onload=null;this.rel='stylesheet'",
            // as: 'style',
            rel: 'stylesheet',
            // media: 'print',
            // onload: "this.media='all'",
            href: `https://fonts.googleapis.com/css?family=${item}&display=swap`
          }
        }),

        {
          hid: 'fa',
          rel: 'preload',
          as: 'style',
          href: 'https://studio.design/css/font-awesome.min.css',
          onload: "this.onload=null;this.rel='stylesheet'"
        }
      ]
    }
  }
})
</script>

<style scoped>
.container {
  font-size: 20px;
  line-height: 1.5;
}
</style>
