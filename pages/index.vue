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
        abcdefgHIJKLMN0123456789
        この書生の掌の裏うちでしばらくはよい心持に坐っておったが、しばらくすると非常な速力で運転し始めた。
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
        {
          family: 'Montserrat',
          weight: '200'
        },
        {
          family: 'Metal Mania',
          weight: '400'
        },
        // {
        //   family: 'Kosugi',
        //   weight: '400'
        // },
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
            hid: 'googleFonts',
            rel: 'preload',
            onload: "this.onload=null;this.rel='stylesheet'",
            // rel: 'stylesheet',
            as: 'style',
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
  font-size: 30px;
}
</style>
