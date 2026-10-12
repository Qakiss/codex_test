<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)
const closeMenu = () => {
  menuOpen.value = false
}

const dishes = [
  {
    number: '01',
    category: '招牌',
    price: '¥ 168',
    name: '松鼠桂鱼',
    description: '外酥里嫩，酸甜恰到好处',
    image: 'photo-fish',
    size: 'dish-large',
  },
  {
    number: '02',
    category: '时令',
    price: '¥ 88',
    name: '龙井虾仁',
    description: '一口春鲜，茶香清远',
    image: 'photo-shrimp',
    size: 'dish-offset',
  },
  {
    number: '03',
    category: '家常',
    price: '¥ 48',
    name: '蟹粉豆腐',
    description: '细腻鲜甜，暖胃又暖心',
    image: 'photo-tofu',
    size: 'dish-third',
  },
]
</script>

<template>
  <header class="site-header">
    <a class="brand" href="#top" aria-label="巷里首页" @click="closeMenu">
      <span class="brand-mark">巷</span>
      <span class="brand-copy"><strong>巷里</strong><small>江南小馆 · EST. 2016</small></span>
    </a>
    <button
      class="menu-toggle"
      aria-label="打开导航"
      :aria-expanded="menuOpen"
      @click="menuOpen = !menuOpen"
    ><span></span><span></span></button>
    <nav class="main-nav" :class="{ open: menuOpen }" aria-label="主导航">
      <a href="#menu" @click="closeMenu">时令菜单</a>
      <a href="#story" @click="closeMenu">关于巷里</a>
      <a href="#visit" @click="closeMenu">来店指南</a>
      <a class="nav-book" href="#visit" @click="closeMenu">预约席位 <span>↗</span></a>
    </nav>
  </header>

  <main id="top">
    <section class="hero">
      <div class="hero-image"></div>
      <div class="hero-shade"></div>
      <div class="hero-content">
        <p class="eyebrow light"><i></i> 一席江南 · 四时风味</p>
        <h1>把江南的<br><em>好时节</em>，端上桌。</h1>
        <p class="hero-desc">沿着巷子走进来，吃一顿应季的江南菜。<br>让熟悉的味道，慢慢回到生活里。</p>
        <div class="hero-actions"><a class="button button-light" href="#menu">看看今天吃什么 <span>↓</span></a><a class="text-link light-link" href="#story">认识巷里 <span>↗</span></a></div>
      </div>
      <div class="hero-note"><span>杭州 · 小河直街</span><span class="note-line"></span><span>30°18′ N / 120°08′ E</span></div>
      <div class="hero-count"><span>01</span><i></i><span>04</span></div>
    </section>

    <section class="intro section-wrap">
      <div class="intro-label"><span class="section-no">01 /</span><span>OUR PHILOSOPHY</span></div>
      <div class="intro-copy"><h2>好味道不必复杂，<br>只要<span>刚刚好。</span></h2><p>一条老巷，一方小院，几道顺着时令长出来的菜。我们相信，认真对待每一种食材，日常的一餐也会有值得记住的滋味。</p></div>
      <div class="intro-stamp">顺时<br><b>而食</b><small>SEASONAL<br>AND SINCERE</small></div>
    </section>

    <section id="menu" class="menu-section">
      <div class="section-wrap menu-top">
        <div><div class="intro-label"><span class="section-no">02 /</span><span>IN SEASON</span></div><h2 class="section-title">此刻的<span>江南味</span></h2></div>
        <a class="text-link" href="#visit">完整菜单 <span>↗</span></a>
      </div>
      <div class="dish-grid">
        <article v-for="dish in dishes" :key="dish.number" class="dish-card" :class="dish.size">
          <div class="dish-photo" :class="dish.image"></div>
          <div class="dish-meta"><span>{{ dish.number }} / {{ dish.category }}</span><span>{{ dish.price }}</span></div>
          <h3>{{ dish.name }}</h3><p>{{ dish.description }}</p>
        </article>
      </div>
      <div class="season-note"><span>✳</span> 每日菜单随季节与市场而变化</div>
    </section>

    <section id="story" class="story-section">
      <div class="story-image"></div>
      <div class="story-content"><div class="intro-label"><span class="section-no">03 /</span><span>THE STORY OF LANE</span></div><p class="story-kicker">一条巷子，一桌家常</p><h2>从田间到餐桌，<br>让每一口都<span>有来处。</span></h2><p class="story-body">每天清晨，我们去熟悉的菜场挑选当季食材。湖里的鱼、山间的笋、刚摘下的青菜——不赶远路，不做复杂，只把它们最好的样子留在盘子里。</p><a class="text-link" href="#visit">巷里的日常 <span>↗</span></a><div class="story-caption">厨房里的一天 · 07:18 AM</div></div>
    </section>

    <section class="quote-section"><div class="quote-mark">“</div><blockquote>日子慢一点，<br>饭菜香一点。</blockquote><p>愿你在巷里，吃得自在。</p><div class="quote-rule"></div></section>

    <section id="visit" class="visit-section section-wrap">
      <div class="visit-heading"><div class="intro-label"><span class="section-no">04 /</span><span>COME FIND US</span></div><h2>巷子不深，<br><span>好味道不远。</span></h2><p>留一张桌，等你来吃饭。</p></div>
      <div class="visit-details"><div class="detail-row"><span>地址</span><p>杭州市拱墅区小河直街 58 号<br>沿河往里，见青砖门头</p></div><div class="detail-row"><span>营业时间</span><p>午市 11:00 — 14:00<br>晚市 17:00 — 21:30</p></div><div class="detail-row"><span>订座电话</span><p><a href="tel:057188806688">0571 — 8880 6688</a></p></div><a class="button button-dark" href="tel:057188806688">现在预约 <span>↗</span></a></div>
      <div class="visit-image"><div class="map-pin">巷里<br><small>杭州 · 小河直街</small></div></div>
    </section>
  </main>

  <footer class="site-footer"><a class="brand footer-brand" href="#top"><span class="brand-mark">巷</span><span class="brand-copy"><strong>巷里</strong><small>江南小馆 · EST. 2016</small></span></a><p>一饭一蔬，四时有味。</p><span class="copyright">© 2025 巷里江南小馆</span><a class="back-top" href="#top">回到顶部 ↑</a></footer>
</template>
