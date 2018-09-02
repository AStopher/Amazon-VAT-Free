// ==UserScript==
// @name         Amazon Show VAT-Free Prices
// @namespace    http://alexanderstopher.com
// @version      0.1
// @description  Shows VAT-free prices on Amazon. Only shows for items in your basket, as well as basket total.
// @author       Alexander Stopher
// @match        *.amazon.co.uk/*
// @grant        none
// @require      https://code.jquery.com/jquery-3.3.1.min.js
// ==/UserScript==

(function() {
    'use strict';
    var $ = window.jQuery;
    $(".sc-price, #priceblock_ourprice").each(function() {
        if ($("#merchant-info").text().indexOf("Amazon") > -1)
        {
            showVatFreePrice(this);
            $("#priceBadging_feature_div").css("font-size", "12px");
        }
        else if (window.location.href.indexOf("www.amazon.co.uk/gp/cart/view.html") > -1)
        {
            showVatFreePrice($(this));
        }
    });

    function showVatFreePrice(t)
    {
        $(t).html("£" + (Number(($(t).text().replace(/[^0-9.-]+/g,"")))/1.2).toFixed(2) + " <sup>(inc. VAT: " + $(t).text() + ")</sup>");
    }

    if (window.location.href.indexOf("www.amazon.co.uk/gp/cart/view.html") > -1)
    {
        $("#cart-about-cart-warning").html($("#cart-about-cart-warning").html() + "The \"VAT-free Prices\" plugin does not guarantee that the prices shown are what you will pay. As a result, this tool does not modify prices shown within the checkout process as a safeguard. We are not liable for any incorrect charges as a result of you using this tool.<br /><br />");
    }
})();
