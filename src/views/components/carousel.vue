<style>
    .demo-carousel{
        height: 200px;
        line-height: 200px;
        text-align: center;
        color: #fff;
        font-size: 20px;
        background: #506b9e;
    }
</style>
<template>
    <i-article>
        <article>
            <h1>Carousel 走马灯</h1>
            <Anchor title="概述" h2></Anchor>
            <p>常用于一组图片或卡片轮播，当内容空间不足时，可以用走马灯的形式进行收纳，进行轮播展现。</p>
            <Anchor title="代码示例" h2></Anchor>
            <Demo title="基础用法">
                <div slot="demo">
                    <Carousel>
                        <Carousel-item>
                            <div class="demo-carousel">1</div>
                        </Carousel-item>
                        <Carousel-item>
                            <div class="demo-carousel">2</div>
                        </Carousel-item>
                        <Carousel-item>
                            <div class="demo-carousel">3</div>
                        </Carousel-item>
                        <Carousel-item>
                            <div class="demo-carousel">4</div>
                        </Carousel-item>
                    </Carousel>
                </div>
                <div slot="desc">
                    <p>最基本的用法。</p>
                </div>
                <i-code lang="html" slot="code">{{ code.base }}</i-code>
            </Demo>
            <Demo title="自动切换">
                <div slot="demo">
                    <Carousel autoplay>
                        <Carousel-item>
                            <div class="demo-carousel">1</div>
                        </Carousel-item>
                        <Carousel-item>
                            <div class="demo-carousel">2</div>
                        </Carousel-item>
                        <Carousel-item>
                            <div class="demo-carousel">3</div>
                        </Carousel-item>
                        <Carousel-item>
                            <div class="demo-carousel">4</div>
                        </Carousel-item>
                    </Carousel>
                </div>
                <div slot="desc">
                    <p>设置属性 <code>autoplay</code> 可以自动轮播，同时可以设置属性 <code>autoplay-speed</code> 改变自动播放的速度。</p>
                </div>
                <i-code lang="html" slot="code">{{ code.autoplay }}</i-code>
            </Demo>
            <Demo title="综合设置">
                <div slot="demo">
                    <i-form :model="setting" :label-width="100">
                        <Form-item label="自动切换">
                            <Switch :checked.sync="setting.autoplay">
                                <span slot="open">开</span>
                                <span slot="close">关</span>
                            </Switch>
                        </Form-item>
                        <Form-item label="自动切换速度">
                            <Slider :value.sync="setting.autoplaySpeed" :min="300" :max="10000" :step="100"></Slider>
                        </Form-item>
                        <Form-item label="指示器位置">
                            <Radio-group :model.sync="setting.dots" type="button">
                                <Radio value="inside">内部</Radio>
                                <Radio value="outside">外部</Radio>
                                <Radio value="none">不显示</Radio>
                            </Radio-group>
                        </Form-item>
                        <Form-item label="切换箭头">
                            <Radio-group :model.sync="setting.arrow" type="button">
                                <Radio value="hover">悬停时显示</Radio>
                                <Radio value="always">一直显示</Radio>
                                <Radio value="never">不显示</Radio>
                            </Radio-group>
                        </Form-item>
                        <Form-item label="指示器触发方式">
                            <Radio-group :model.sync="setting.trigger" type="button">
                                <Radio value="click">点击</Radio>
                                <Radio value="hover">悬停</Radio>
                            </Radio-group>
                        </Form-item>
                    </i-form>
                    <Carousel
                        :autoplay="setting.autoplay"
                        :autoplay-speed="setting.autoplaySpeed"
                        :dots="setting.dots"
                        :trigger="setting.trigger"
                        :arrow="setting.arrow">
                        <Carousel-item>
                            <div class="demo-carousel">1</div>
                        </Carousel-item>
                        <Carousel-item>
                            <div class="demo-carousel">2</div>
                        </Carousel-item>
                        <Carousel-item>
                            <div class="demo-carousel">3</div>
                        </Carousel-item>
                        <Carousel-item>
                            <div class="demo-carousel">4</div>
                        </Carousel-item>
                    </Carousel>
                </div>
                <div slot="desc">
                    <p>动态调整各配置。</p>
                </div>
                <i-code lang="html" slot="code">{{ code.setting }}</i-code>
            </Demo>
            <div class="api">
                <Anchor title="API" h2></Anchor>
                <Anchor title="Carousel props" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>属性</th>
                            <th>说明</th>
                            <th>类型</th>
                            <th>默认值</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>current-index</td>
                            <td>幻灯片的索引，从 0 开始</td>
                            <td>Number</td>
                            <td>0</td>
                        </tr>
                        <tr>
                            <td>height</td>
                            <td>走马灯的高度，可填 auto 或具体高度数值，单位 px</td>
                            <td>String | Number</td>
                            <td>auto</td>
                        </tr>
                        <tr>
                            <td>autoplay</td>
                            <td>是否自动切换</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>autoplay-speed</td>
                            <td>自动切换的时间间隔，单位为毫秒</td>
                            <td>Number</td>
                            <td>2000</td>
                        </tr>
                        <tr>
                            <td>dots</td>
                            <td>指示器的位置，可选值为 inside （内部），outside（外部），none（不显示）</td>
                            <td>String</td>
                            <td>inside</td>
                        </tr>
                        <tr>
                            <td>trigger</td>
                            <td>指示器的触发方式，可选值为 click（点击），hover（悬停）</td>
                            <td>String</td>
                            <td>click</td>
                        </tr>
                        <tr>
                            <td>arrow</td>
                            <td>切换箭头的显示时机，可选值为 hover（悬停），always（一直显示），never（不显示）</td>
                            <td>String</td>
                            <td>hover</td>
                        </tr>
                        <tr>
                            <td>easing</td>
                            <td>动画效果</td>
                            <td>String</td>
                            <td>ease</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="Carousel events" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>事件名</th>
                            <th>说明</th>
                            <th>返回值</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>on-change</td>
                            <td>幻灯片切换时触发，目前激活的幻灯片的索引，原幻灯片的索引</td>
                            <td>oldValue, value</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </article>
    </i-article>
</template>
<script>
    import iArticle from '../../components/article.vue';
    import iCode from 'iCode';
    import Demo from '../../components/demo.vue';
    import Code from '../../code/carousel';
    import Anchor from '../../components/anchor.vue';

    export default {
        components: {
            iArticle,
            iCode,
            Demo,
            Anchor
        },
        data () {
            return {
                code: Code,
                setting: {
                    autoplay: false,
                    autoplaySpeed: 2000,
                    dots: 'inside',
                    trigger: 'click',
                    arrow: 'hover'
                }
            }
        },
        methods: {

        }
    };
</script>