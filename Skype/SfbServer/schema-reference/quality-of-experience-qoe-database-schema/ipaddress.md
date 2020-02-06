---
title: IPAddress 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 테이블은 경력 데이터베이스의 다른 곳에 사용 되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809546"
---
# <a name="ipaddress-table"></a><span data-ttu-id="1bd92-104">IPAddress 테이블</span><span class="sxs-lookup"><span data-stu-id="1bd92-104">IPAddress table</span></span>
 
<span data-ttu-id="1bd92-105">IPAddress 테이블은 경력 데이터베이스의 다른 곳에 사용 되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd92-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="1bd92-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd92-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="1bd92-107">**열**</span><span class="sxs-lookup"><span data-stu-id="1bd92-107">**Column**</span></span>|<span data-ttu-id="1bd92-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="1bd92-108">**Data Type**</span></span>|<span data-ttu-id="1bd92-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="1bd92-109">**Key/Index**</span></span>|<span data-ttu-id="1bd92-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="1bd92-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1bd92-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="1bd92-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="1bd92-112">int</span><span class="sxs-lookup"><span data-stu-id="1bd92-112">int</span></span>  <br/> |<span data-ttu-id="1bd92-113">주요한</span><span class="sxs-lookup"><span data-stu-id="1bd92-113">Primary</span></span>  <br/> |<span data-ttu-id="1bd92-114">지정 된 IP 주소에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1bd92-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="1bd92-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="1bd92-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="1bd92-116">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="1bd92-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="1bd92-117">독특한</span><span class="sxs-lookup"><span data-stu-id="1bd92-117">Unique</span></span>  <br/> |<span data-ttu-id="1bd92-118">IpAddressKey에 매핑되는 고유 IP 주소 (예: 189.168.1.1)입니다.</span><span class="sxs-lookup"><span data-stu-id="1bd92-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="1bd92-119">IPv4 또는 IPv6 주소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd92-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

