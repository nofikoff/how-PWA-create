#PWA
PWA - это своего рода приложение, устанавливаемое из браузера, которое может предоставить дополнительные функции, основанные на возможностях используемого устройства: сайт может работать автономно оффлайн, делать push-уведомления и выглядеть и работать почти так же быстро, как и отдельное приложение.

Разработчики имеют возможность создавать практически первоклассные приложения с использованием веб-технологий, что всегда значительно проще и дешевле в обслуживании, чем создание собственных приложений. Особенное преимущество PWA - кроссплатформенность. Также одним из преимуществ можно выделить отсутвие необходимости готовое приложение регистрировать в маркетах приложений (таких как Google Play Маркет и App Store), так как приложение устанавливается на телефоне прямо из браузера).

Таким образом PWA - это веб-сайт, который разработан с использованием технологий, что делают опыт взаимодействия с контентом сайта на мобильных устройствах намного приятнее, чем с обычным сайтом, оптимизированном под мобильные устройства. В то же время PWA работает почти как нативное приложение, так как обладает следующими функциями:

- Работа в оффлайне
- Быстрая загрузка
- Работа по защищенному протоколу
- Умеет в push-уведомления
- Может выглядеть как полноценное приложение без строки адреса в браузере (например, как этот крайне красивый сайт)


Если это Вордпресс, не морочим голову ставим плагин https://wordpress.org/plugins/super-progressive-web-apps/
В исхоДном коде WP подсматриваем как выглядит идеальный manifest

# Иначе по инструкции:
- Переносим в корень проекта sw.js
- Режем иконки с помощью сервиса https://www.favicon-generator.org/ подключаем их в head проекта. (не забудь 512х512)
- Создаем манифест, подключаем его в head проекта  <link rel="manifest" href="/manifest.json">
- В head проекта указываем
<script>
if (navigator.serviceWorker.controller) {
  console.log('[PWA Builder] active service worker found, no need to register')
} else {
  navigator.serviceWorker.register('sw.js', {
    scope: './'
  }).then(function(reg) {
    console.log('Service worker has been registered for scope:'+ reg.scope);
  });
}
</script>


# Тестируем PWA через
- Хром / аудит
- https://www.pwabuilder.com/ здесь тюнинг и дополнительные фичи

Источник https://www.runovikov.ru/?p=92 
