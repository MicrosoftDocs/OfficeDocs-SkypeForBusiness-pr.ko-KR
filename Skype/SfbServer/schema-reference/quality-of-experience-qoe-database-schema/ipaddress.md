---
title: IPAddress 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 테이블은 QoE(체감 품질) 데이터베이스의 모든 위치에서 사용되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802778"
---
# <a name="ipaddress-table"></a><span data-ttu-id="d68c2-104">IPAddress 테이블</span><span class="sxs-lookup"><span data-stu-id="d68c2-104">IPAddress table</span></span>
 
<span data-ttu-id="d68c2-105">IPAddress 테이블은 QoE(체감 품질) 데이터베이스의 모든 위치에서 사용되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d68c2-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="d68c2-106">이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d68c2-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d68c2-107">**열**</span><span class="sxs-lookup"><span data-stu-id="d68c2-107">**Column**</span></span>|<span data-ttu-id="d68c2-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="d68c2-108">**Data Type**</span></span>|<span data-ttu-id="d68c2-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="d68c2-109">**Key/Index**</span></span>|<span data-ttu-id="d68c2-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="d68c2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d68c2-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="d68c2-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="d68c2-112">int</span><span class="sxs-lookup"><span data-stu-id="d68c2-112">int</span></span>  <br/> |<span data-ttu-id="d68c2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d68c2-113">Primary</span></span>  <br/> |<span data-ttu-id="d68c2-114">지정된 IP 주소의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d68c2-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="d68c2-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="d68c2-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="d68c2-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="d68c2-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="d68c2-117">고유</span><span class="sxs-lookup"><span data-stu-id="d68c2-117">Unique</span></span>  <br/> |<span data-ttu-id="d68c2-p103">IpAddressKey에 매핑되는 고유 IP 주소(예: 189.168.1.1)입니다. IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d68c2-p103">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

