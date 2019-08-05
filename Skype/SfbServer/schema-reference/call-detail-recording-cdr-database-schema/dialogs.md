---
title: 비즈니스용 Skype 서버 2015의 대화 상자 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs 테이블은 피어 투 피어 세션에 대 한 DialogIDs에 대 한 정보를 저장 하는 지원 테이블입니다.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196763"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="851cf-103">비즈니스용 Skype 서버 2015의 대화 상자 테이블</span><span class="sxs-lookup"><span data-stu-id="851cf-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="851cf-104">Dialogs 테이블은 피어 투 피어 세션에 대 한 DialogIDs에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="851cf-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="851cf-105">**열**</span><span class="sxs-lookup"><span data-stu-id="851cf-105">**Column**</span></span>|<span data-ttu-id="851cf-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="851cf-106">**Data Type**</span></span>|<span data-ttu-id="851cf-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="851cf-107">**Key/Index**</span></span>|<span data-ttu-id="851cf-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="851cf-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="851cf-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="851cf-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="851cf-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="851cf-110">datetime</span></span>  <br/> |<span data-ttu-id="851cf-111">주요한</span><span class="sxs-lookup"><span data-stu-id="851cf-111">Primary</span></span>  <br/> |<span data-ttu-id="851cf-112">세션 요청 시간 세션을 고유 하 게 식별 하는 SessionIDSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="851cf-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="851cf-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="851cf-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="851cf-114">int</span><span class="sxs-lookup"><span data-stu-id="851cf-114">int</span></span>  <br/> |<span data-ttu-id="851cf-115">주요한</span><span class="sxs-lookup"><span data-stu-id="851cf-115">Primary</span></span>  <br/> |<span data-ttu-id="851cf-116">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="851cf-116">ID number to identify the session.</span></span> <span data-ttu-id="851cf-117">세션을 고유 하 게 식별 하는 SessionIDTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="851cf-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="851cf-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="851cf-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="851cf-119">int</span><span class="sxs-lookup"><span data-stu-id="851cf-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="851cf-120">ExternalID의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="851cf-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="851cf-121">이 필드는 데이터베이스 검색 속도를 높이는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="851cf-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="851cf-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="851cf-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="851cf-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="851cf-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="851cf-124">이진으로 저장 된 SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="851cf-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="851cf-125">이진 파일의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="851cf-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="851cf-126">대화 상자; from 태그; 태그</span><span class="sxs-lookup"><span data-stu-id="851cf-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="851cf-127">이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851cf-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

