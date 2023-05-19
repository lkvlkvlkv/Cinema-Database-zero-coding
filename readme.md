# 電影院訂票系統(0程式)

## 0程式

放上來只是覺得做得滿認真的，當作備份(?)

## 報告連結

[HackMD網址](https://hackmd.io/@LKV/database_final_project)

## ER-Model連結

[連結](https://drive.google.com/file/d/1VXONNLJPomRvLIeH5kTiTrSRq_37hdde/view)

## 使用方法(雖然我不知道為甚麼要用)

把MySQL_Create_table裡的東西全部一個一個丟去sql create table
再把init_every_tables裡的東西全部一個一個丟去sql insert element

因為一些foreign key的Constraint，create table有順序的問題(拓樸感)

Movies > MovieSessions = Actors = Showing
Cinemas > Showing = Theaters > MovieSessions = Seats > BookingSeats = Orders = TicketInfo
Members > Orders

modify_after_create_booking_seats要最後跑，讓一些被訂購的位置is_reserved=1