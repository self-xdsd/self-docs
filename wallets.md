---
layout: default
title: Wallets, Payments and Invoicing
nav_order: 6
---

# Wallets, Payments and Invoicing

<a href="#the-fake-wallet">The Fake Wallet</a><br>
<a href="#the-real-wallet">The Real Wallet</a><br>
<a href="#payments">Payments</a><br>
<a href="#invoicing">Invoicing</a>

## The Fake Wallet

Each project managed by Self XDSD starts off with a **Fake Wallet** which has **100.000,00 €** in it.
You can work with it until you decide to use a **Real Wallet**. Think of it as a dry run, or free trial,
where you can enjoy all the functionalities of Self XDSD without paying any money.

Of course, your contributors might not be so motivated to work in this scenario. We recommend you switch
to a real wallet as soon as possible.

## The Real Wallet

Self XDSD integrates with [Stripe](https://stripe.com) to provide payment functionalities. Registering a real wallet means
sending your billing and card information to Stripe, which will use them on our behalf to make payments. Self XDSD does not maintain any sensitive information such as card details.

Once you register a real wallet and a payment method (a credit or debit card), you have to specify a **cash Limit** -- that is
exactly how much money Self XDSD will use. You will have to update this limit regularly and we also kindly ask you to make sure
that you actually have that amount of money available on your card.

## Payments

Each Monday, Self XDSD will automatically pay all the Invoices which have a value over **100,00 €**. You can also pay an Invoice manually from the web UI, once its value is over **100,00 €**.

Of course, if you are using a fake wallet, the payments will be fictive -- nobody will pay or receive any money, we will just mark the Invoice as "paid".

## Invoicing

On the Project page, Contracts tab, you can download all the Invoices from your contributors. These invoices contain both the Contributor's revenue and Self XDSD's commission. All your spent money should be covered by these invoices.

If you are using a fake wallet, these invoices will be addressed to "Project xxxxx/yyyyy at Github.", so they will not have any fiscal value (this makes sense, since no actual payments are performed). When you register a real wallet, you will be asked for your business and/or tax information, which will appear on the invoice. The Contributor is also asked for their business/tax information when registering with Stripe.

For all the invoices paid with the real wallet, the Contributor will receive invoices from Self XDSD covering the commission -- they will be able to use these invoices to deduct the commission from their books.
