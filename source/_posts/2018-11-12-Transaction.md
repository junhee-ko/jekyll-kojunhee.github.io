---
layout: post
title:  "Transaction"
date:   2018-11-12
categories: database
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dbDoorImg.png
---

## 트랜잭션이란

하나의 논리적인 작업 단위를 구성하는 연산들의 집합

## ACID

1. Atomicity

   만약 트랜잭션 중간에 어떠한 문제가 발생한다면 트랜잭션에 해당하는 어떠한 작업 내용도 수행되어서는 안되
   며, 아무런 문제가 발생되지 않았을 경우에만 모든 작업이 수행되어야 한다.

2. Consistency

   트랜잭션이 완료된 다음의 상태에서도 트랜잭션이 일어나기 전의 상황과 동일하게 데이터의 일관성을 보장해
   야 한다. 

   예를 들어 계좌이체를 성공적으로 실행했다면, A계좌의 잔액과 B계좌의 잔액의 합이 트랜잭션 실행 전의 합
   과 동일해야한다.

3. Isolation

   각각의 트랜잭션은 서로 간섭없이 독립적으로 수행되어야 한다.

4. Durability

   트랜잭션이 정상적으로 종료된 다음에는 영구적으로 데이터베이스에 작업의 결과가 저장되어야 한다.

## Commit, Rollback

1. Commit

   모든 작업을 정상적으로 처리하겠다고 확정하는 명령어이다. 트랜젝션의 처리 과정을 데이터베이스에 반영하
   기 위해서, 변경된 내용을 모두 영구 저장한다.

2. Rollback

   작업 중 문제가 발생했을 때, 트랜젝션의 처리 과정에서 발생한 변경 사항을 취소하고, 트랜젝션 과정을 종료
   시킨는 명령어이다. 트랜젝션으로 인한 하나의 묶음 처리가 시작되기 이전의 상태로 되돌린다.

## Reference

<https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/Database#transaction>

<https://wikidocs.net/4096>