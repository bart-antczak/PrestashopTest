<!--**
 * 2007-2020 PrestaShop SA and Contributors
 *
 * NOTICE OF LICENSE
 *
 * This source file is subject to the Open Software License (OSL 3.0)
 * that is bundled with this package in the file LICENSE.txt.
 * It is also available through the world-wide-web at this URL:
 * https://opensource.org/licenses/OSL-3.0
 * If you did not receive a copy of the license and are unable to
 * obtain it through the world-wide-web, please send an email
 * to license@prestashop.com so we can send you a copy immediately.
 *
 * DISCLAIMER
 *
 * Do not edit or add to this file if you wish to upgrade PrestaShop to newer
 * versions in the future. If you wish to customize PrestaShop for your
 * needs please refer to https://www.prestashop.com for more information.
 *
 * @author    PrestaShop SA <contact@prestashop.com>
 * @copyright 2007-2020 PrestaShop SA and Contributors
 * @license   https://opensource.org/licenses/OSL-3.0 Open Software License (OSL 3.0)
 * International Registered Trademark & Property of PrestaShop SA
 *-->
<template>
  <nav aria-label="Breadcrumb">
    <ol class="breadcrumb">
      <li class="breadcrumb-item">
        <a :href="catalogLink">{{trans('link_catalog')}}</a>
      </li>
      <li class="breadcrumb-item">
        <a :href="stockLink">{{trans('link_stock')}}</a>
      </li>
      <li class="breadcrumb-item active">
        <span v-if="isOverview">{{trans('link_overview')}}</span>
        <span v-else>{{trans('link_movements')}}</span>
      </li>
    </ol>
  </nav>
</template>

<script>
  export default {
    computed: {
      isOverview() {
        return this.$route.name === 'overview';
      },
      catalogLink() {
        return window.data.catalogUrl;
      },
      stockLink() {
        return window.data.stockUrl;
      },
    },
  };
</script>
