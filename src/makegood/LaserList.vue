<template>
       <works-render :works="works"/>

</template>

<script>
import WorksRender from './WorksRender.vue';

  export default {
      components: {
    WorksRender,
  },
    data () {
      return {
        works: [
          {
            name: "Кружки с гравировкой",
            buyer: "ООО «Трудовой Арбитраж»",
            description:"Заказчик обратилося с чёткой задачей: нужно изготовить кружки с логотипом для сотрудников в качестве корпоративных подарков. Мы предлодложили 3-4 варианта, один из которых ребята утвердили. А именно: кружка с покрытием soft-touch с гравировкой их логотипа. При выполнении заказа мы использовали новый станок с механизмом круговой гравировки, что позволило разместить логотип на максимальной площади кружки. Кстати, на заднем плане на фото календарь-додекаэдр из дерева. Тоже наша работа, но для другого заказчика)",
            imageUrl: "https://laser.makegood.group/wp-content/uploads/2021/02/%D0%9A%D1%80%D1%83%D0%B6%D0%BA%D0%B0-%D1%81-%D0%BB%D0%BE%D0%B3%D0%BE%D1%82%D0%B8%D0%BF%D0%BE%D0%BC-%D0%BE%D1%82-%D0%B7%D0%B0%D0%BA%D0%B0%D0%B7%D1%87%D0%B8%D0%BA%D0%B0.jpeg",
            dialog: false,
          },
          {
            name: "Гравировка на зажигалке",
            buyer: "Александра нашла нас в ВК =)",
            description:"С задачей успешно справились, зажигалку отгравировали. Молодой человек Александры был доволен подарком)",
            imageUrl: "https://laser.makegood.group/wp-content/uploads/2021/02/%D0%9D%D0%B0%D1%88%D0%B5-%D1%84%D0%BE%D1%82%D0%BE-1-scaled.jpg",
            dialog: false,
          },
                    {
            name: "Меню из дерева",
            buyer: "Кафе-пиццерия «A’Rome»",
            description:"Взяли за основу макет обложки для ежедневника с гравировкой логотипа на лицевой стороне. Обработали специальным составом, включающим масло и воск, что дало водоотталкивающие свойства и приятный цвет. Блок меню напечатали на синтетической бумаге, которой также не страшна вода и масло (протестировано нами и самим заказчиком при выборе материалов). Крепеление блока сделали на кольцевом механизме. Это позволит в дальнейшем без проблем менять информацию в меню без перепечатки всего блока.",
            imageUrl: "https://laser.makegood.group/wp-content/uploads/2021/02/%D0%9D%D0%B0%D1%88%D0%B5-%D1%84%D0%BE%D1%82%D0%BE-2-scaled.jpg",
            dialog: false,
          },
                    {
            name: "Гравировка на бокалах",
            buyer: "Бар «Пятница»",
            description:"Ребята обратились с предложением сделать гравировку на их бокалах. Выбрали оптимальные размеры для каждого вида посуды таким образом, чтобы на каждом варианте логотип просматривался и читался одинаково хорошо. Пришлось пожертвовать одной рюмкой при «приладке», в остальном всё прошло отлично",
            imageUrl: "https://laser.makegood.group/wp-content/uploads/2021/02/%D0%93%D1%80%D0%B0%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BD%D0%B0-%D0%B1%D0%BE%D0%BA%D0%B0%D0%BB%D0%B0-%D0%BE%D1%82-%D0%B7%D0%B0%D0%BA%D0%B0%D0%B7%D1%87%D0%B8%D0%BA%D0%B0.jpeg",
            dialog: false,
          },
                    {
            name: "Термокружки",
            buyer: " ",
            description:"Мы поддерживаем крутую идею покупать кофе в своих термосах и коферах, чтобы снизить потребление одноразовой посуды. Предлагаем сделать это оригинально! Как насчёт термоса со своим именем или любимым сериалом? А ещё этот подарок подойдёт тому самому другу фрилансеру!",
            imageUrl: "https://laser.makegood.group/wp-content/uploads/2022/04/photo_2022-04-26_09-56-14.jpg",
            dialog: false,
          },
          

        ],
      }
    },

  }
</script>

<style>
.title {
  position: relative;
  text-align: center;
  transform: translateZ(0);
  transform-style: preserve-3d;
}

.title .text {
  font-family: sans-serif;
  font-weight: 400;
  font-size: calc(20vw / var(--word-total) );
  line-height: 1.0;
}

.title .write .word {
  color: hsl(0, 0%, 80%);
  text-shadow: 0 0 0.1em currentColor;
  transform-style: preserve-3d;
  animation: write linear both;
}

.title .laser {
  position: absolute;
  top: 0;
  left: 0;
  /* To avoid the blur getting masked by the clip-path we had to duplicate the element */
  filter: blur(4px) contrast(10);
  pointer-events: none;
}

.title .laser .word {
  display: inline-block;
}

.title .laser .word {
  color: hsl(0, 100%, 75%);
  text-shadow: 0 0 0.1em currentColor;
  transform: translateZ(5px);
  animation: laser linear both;
}

.title .write .word,
.title .laser .word {
  animation-duration: 4s;
  animation-delay: calc(0.3s + var(--word-index) * 160ms);
  animation-iteration-count: infinite;
}

.title:hover .word {
  animation-play-state: paused;
}

.title .text .word,
.title .text .word::before {
  animation-play-state: paused;
  animation-delay: -0.4s;
}

@keyframes write {
  from, 30% { clip-path: polygon(-20% 0%, -15% 0%, -15% 100%, -20% 100%) }
  70%, to { clip-path: polygon(-15% 0%, 120% 0%, 120% 100%, -15% 100%) }
}

@keyframes laser {
  from, 30% { clip-path: polygon(-20% 0%, -15% 0%, -15% 100%, -20% 100%) }
  70%, to { clip-path: polygon(115% 0%, 120% 0%, 120% 100%, 115% 100%) }
}
</style>