---
title: 업로드 품질 대시보드(CQD)에서 테넌트 및 건물 데이터 관리
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: CQD(통화 품질 대시보드)에서 테넌트 및 건물 데이터를 업로드하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 7a1f6de78e01a8988317aa99aae917aa0018e19a
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067143"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="3be35-103">업로드 품질 대시보드(CQD)에서 테넌트 및 건물 데이터 관리</span><span class="sxs-lookup"><span data-stu-id="3be35-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="3be35-104">CQD(통화 품질 대시보드)를 가장 잘 사용하려면 테넌트 및 건물 데이터를 업로드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="3be35-105">테넌트 데이터 파일, 건물 및 엔드포인트에는 [2가지](#upload-building-data-file) [유형이 있습니다.](#endpoint-data-file)</span><span class="sxs-lookup"><span data-stu-id="3be35-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="3be35-106">여기에서 샘플 테넌트 데이터 템플릿을 다운로드할 수 [있습니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="3be35-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="3be35-107">건물 매핑에 대한 도움말은 [CQD에 대한 건물 맵 만들기 를 읽어보아야 합니다.](CQD-building-mapping.md)</span><span class="sxs-lookup"><span data-stu-id="3be35-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="3be35-108">CQD 요약 보고서 **대시보드에서** CQD 업로드 메뉴에서 테넌트  데이터 설정(CQD 맨 위에 있는 기어 아이콘)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="3be35-109">여기에서 관리자는 IP 주소 및 지리적 정보 매핑, 각 무선 액세스 지점 및 해당 MAC 주소 매핑과 같은 조직의 건물 및 엔드포인트 정보를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="3be35-110">CQD(Teams 관리 센터 또는 에서)를 연 다음 오른쪽 위 모서리에서 기어 아이콘을 선택하고 요약 보고서 페이지에서 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) **테넌트 업로드** 선택하세요. </span><span class="sxs-lookup"><span data-stu-id="3be35-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![데이터가 업로드되는 동안 나타나는 대화 상자 스크린샷](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="3be35-112">또는 처음 CQD를 방문하는 경우 건물 데이터를 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="3be35-113">지금 **시작을 선택하여 테넌트** 데이터 업로드 페이지로 **빠르게** 업로드 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![사용자에게 건물 데이터를 업로드하도록 고지하는 배너 스크린샷](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="3be35-115">**테넌트** 데이터 업로드 페이지에서 찾아보기를 선택하여 데이터 파일을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="3be35-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="3be35-116">데이터 파일을 선택한 후  시작 날짜를 지정하고, 선택적으로 종료 날짜를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="3be35-117">시작 **날짜를** 선택한  업로드 CQD에 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-117">After selecting **Start date**, select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="3be35-118">파일이 업로드되기 전에 유효성이 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="3be35-119">유효성 검사가 실패하면 파일을 수정해야 하는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="3be35-120">다음 그림은 데이터 파일의 열 수가 올바르지 않은 경우 발생하는 오류를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![건물 데이터 업로드 오류를 표시하는 대화 상자의 예](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="3be35-122">유효성 검사 중에 오류가 발생하지 않은 경우 파일 업로드가 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="3be35-123">그런 다음 내 업로드 테이블에서  업로드된 데이터 파일을 볼 수 있습니다. 이 페이지 아래쪽에 있는 현재 테넌트에 대해 업로드된 모든 파일의 전체 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="3be35-124">건물 파일 처리를 완료하는 데 최대 4시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="3be35-125">건물 파일을 이미 업로드하고 누락되거나 제외된 서브넷을 추가해야 하는 경우 새 서브넷을 추가하여 원본 파일을 수정하고, 현재 파일을 제거한 다음 새로 편집한 파일을 다시 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="3be35-126">CQD에는 하나의 활성 건물 데이터 파일이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="3be35-127">업로드 파일 구성</span><span class="sxs-lookup"><span data-stu-id="3be35-127">Upload building data file</span></span>

<span data-ttu-id="3be35-128">CQD의 테넌트 데이터 파일의 첫 번째 형식은 건물 **데이터** 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="3be35-129">서브넷 열은 Network+NetworkRange 열을 확장한 다음 호출 레코드의 첫 번째 서브넷 또는 두 번째 서브넷 열에 서브넷 열을 조인하여 건물, 도시, 국가 또는 지역 정보를 표시하여 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="3be35-130">업로드하는 데이터 파일의 형식은 업로드하기 전에 유효성 검사 검사를 통과하기 위해 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="3be35-131">파일은 .tsv 파일(열은 TAB으로 구분) 또는 .csv 파일(열은 콤마로 구분)되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="3be35-132">데이터 파일에는 테이블 헤더 행이 포함되어 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="3be35-133">데이터 파일의 첫 번째 줄은 "네트워크"처럼 헤더 레이블이 아닌 실제 데이터로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="3be35-134">파일의 데이터 형식은 문자열, 정수 또는 부울일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="3be35-135">정수 데이터 형식의 경우 값은 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="3be35-136">부울 값은 0 또는 1이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="3be35-137">열에서 문자열 데이터 형식을 사용하는 경우 데이터 필드는 비어 있을 수 있지만 여전히 탭 또는 콤마로 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="3be35-138">빈 데이터 필드는 빈 문자열 값을 할당하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="3be35-139">테넌트 데이터 파일당 1,000,000개 확장된 행 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-139">There is a 1,000,000 expanded row limit per tenant data file.</span></span>

- <span data-ttu-id="3be35-140">각 행에 대해 15개 열이 있어야 합니다. 각 열에는 적절한 데이터 형식이 있어야 합니다. 열은 다음 표에 나열된 순서(콤마 또는 탭 설명)에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-140">There must be 15 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="3be35-141">**데이터 파일 형식 구축**</span><span class="sxs-lookup"><span data-stu-id="3be35-141">**Building data file format**</span></span>
  
  | <span data-ttu-id="3be35-142">열 이름</span><span class="sxs-lookup"><span data-stu-id="3be35-142">Column name</span></span>        | <span data-ttu-id="3be35-143">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3be35-143">Data type</span></span> | <span data-ttu-id="3be35-144">예제</span><span class="sxs-lookup"><span data-stu-id="3be35-144">Example</span></span>                   | <span data-ttu-id="3be35-145">지침</span><span class="sxs-lookup"><span data-stu-id="3be35-145">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="3be35-146">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="3be35-146">NetworkIP</span></span>          | <span data-ttu-id="3be35-147">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-147">String</span></span>    | <span data-ttu-id="3be35-148">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="3be35-148">192.168.1.0</span></span>               | <span data-ttu-id="3be35-149">필수</span><span class="sxs-lookup"><span data-stu-id="3be35-149">Required</span></span>              |
  | <span data-ttu-id="3be35-150">NetworkName</span><span class="sxs-lookup"><span data-stu-id="3be35-150">NetworkName</span></span>        | <span data-ttu-id="3be35-151">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-151">String</span></span>    | <span data-ttu-id="3be35-152">USA/시애틀/시애틀-SEA-1</span><span class="sxs-lookup"><span data-stu-id="3be35-152">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="3be35-153">필수<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3be35-153">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="3be35-154">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="3be35-154">NetworkRange</span></span>       | <span data-ttu-id="3be35-155">번호</span><span class="sxs-lookup"><span data-stu-id="3be35-155">Number</span></span>    | <span data-ttu-id="3be35-156">26</span><span class="sxs-lookup"><span data-stu-id="3be35-156">26</span></span>                        | <span data-ttu-id="3be35-157">필수</span><span class="sxs-lookup"><span data-stu-id="3be35-157">Required</span></span>              |
  | <span data-ttu-id="3be35-158">BuildingName</span><span class="sxs-lookup"><span data-stu-id="3be35-158">BuildingName</span></span>       | <span data-ttu-id="3be35-159">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-159">String</span></span>    | <span data-ttu-id="3be35-160">시애틀-SEA-1</span><span class="sxs-lookup"><span data-stu-id="3be35-160">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="3be35-161">필수<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3be35-161">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="3be35-162">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="3be35-162">OwnershipType</span></span>      | <span data-ttu-id="3be35-163">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-163">String</span></span>    | <span data-ttu-id="3be35-164">Contoso</span><span class="sxs-lookup"><span data-stu-id="3be35-164">Contoso</span></span>                   | <span data-ttu-id="3be35-165">선택</span><span class="sxs-lookup"><span data-stu-id="3be35-165">Optional</span></span>              |
  | <span data-ttu-id="3be35-166">BuildingType</span><span class="sxs-lookup"><span data-stu-id="3be35-166">BuildingType</span></span>       | <span data-ttu-id="3be35-167">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-167">String</span></span>    | <span data-ttu-id="3be35-168">IT 종료</span><span class="sxs-lookup"><span data-stu-id="3be35-168">IT Termination</span></span>            | <span data-ttu-id="3be35-169">선택</span><span class="sxs-lookup"><span data-stu-id="3be35-169">Optional</span></span>              |
  | <span data-ttu-id="3be35-170">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="3be35-170">BuildingOfficeType</span></span> | <span data-ttu-id="3be35-171">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-171">String</span></span>    | <span data-ttu-id="3be35-172">엔지니어링</span><span class="sxs-lookup"><span data-stu-id="3be35-172">Engineering</span></span>               | <span data-ttu-id="3be35-173">선택</span><span class="sxs-lookup"><span data-stu-id="3be35-173">Optional</span></span>              |
  | <span data-ttu-id="3be35-174">도시</span><span class="sxs-lookup"><span data-stu-id="3be35-174">City</span></span>               | <span data-ttu-id="3be35-175">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-175">String</span></span>    | <span data-ttu-id="3be35-176">시애틀</span><span class="sxs-lookup"><span data-stu-id="3be35-176">Seattle</span></span>                   | <span data-ttu-id="3be35-177">권장</span><span class="sxs-lookup"><span data-stu-id="3be35-177">Recommended</span></span>           |
  | <span data-ttu-id="3be35-178">ZipCode</span><span class="sxs-lookup"><span data-stu-id="3be35-178">ZipCode</span></span>            | <span data-ttu-id="3be35-179">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-179">String</span></span>    | <span data-ttu-id="3be35-180">98001</span><span class="sxs-lookup"><span data-stu-id="3be35-180">98001</span></span>                     | <span data-ttu-id="3be35-181">권장</span><span class="sxs-lookup"><span data-stu-id="3be35-181">Recommended</span></span>           |
  | <span data-ttu-id="3be35-182">국가</span><span class="sxs-lookup"><span data-stu-id="3be35-182">Country</span></span>            | <span data-ttu-id="3be35-183">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-183">String</span></span>    | <span data-ttu-id="3be35-184">미국</span><span class="sxs-lookup"><span data-stu-id="3be35-184">US</span></span>                        | <span data-ttu-id="3be35-185">권장</span><span class="sxs-lookup"><span data-stu-id="3be35-185">Recommended</span></span>           |
  | <span data-ttu-id="3be35-186">상태</span><span class="sxs-lookup"><span data-stu-id="3be35-186">State</span></span>              | <span data-ttu-id="3be35-187">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-187">String</span></span>    | <span data-ttu-id="3be35-188">WA</span><span class="sxs-lookup"><span data-stu-id="3be35-188">WA</span></span>                        | <span data-ttu-id="3be35-189">권장</span><span class="sxs-lookup"><span data-stu-id="3be35-189">Recommended</span></span>           |
  | <span data-ttu-id="3be35-190">지역</span><span class="sxs-lookup"><span data-stu-id="3be35-190">Region</span></span>             | <span data-ttu-id="3be35-191">문자열</span><span class="sxs-lookup"><span data-stu-id="3be35-191">String</span></span>    | <span data-ttu-id="3be35-192">MSUS</span><span class="sxs-lookup"><span data-stu-id="3be35-192">MSUS</span></span>                      | <span data-ttu-id="3be35-193">권장</span><span class="sxs-lookup"><span data-stu-id="3be35-193">Recommended</span></span>           |
  | <span data-ttu-id="3be35-194">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3be35-194">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="3be35-195">Bool</span><span class="sxs-lookup"><span data-stu-id="3be35-195">Bool</span></span>      | <span data-ttu-id="3be35-196">1</span><span class="sxs-lookup"><span data-stu-id="3be35-196">1</span></span>             | <span data-ttu-id="3be35-197">필수</span><span class="sxs-lookup"><span data-stu-id="3be35-197">Required</span></span>              |
  | <span data-ttu-id="3be35-198">ExpressRoute<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="3be35-198">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="3be35-199">Bool</span><span class="sxs-lookup"><span data-stu-id="3be35-199">Bool</span></span>      | <span data-ttu-id="3be35-200">0</span><span class="sxs-lookup"><span data-stu-id="3be35-200">0</span></span>             | <span data-ttu-id="3be35-201">필수</span><span class="sxs-lookup"><span data-stu-id="3be35-201">Required</span></span>              |
  | <span data-ttu-id="3be35-202">VPN</span><span class="sxs-lookup"><span data-stu-id="3be35-202">VPN</span></span>                | <span data-ttu-id="3be35-203">Bool</span><span class="sxs-lookup"><span data-stu-id="3be35-203">Bool</span></span>      | <span data-ttu-id="3be35-204">0</span><span class="sxs-lookup"><span data-stu-id="3be35-204">0</span></span>                         | <span data-ttu-id="3be35-205">선택</span><span class="sxs-lookup"><span data-stu-id="3be35-205">Optional</span></span>              |

  <span data-ttu-id="3be35-206"><sup>1</sup> CQD에서 필요하지는 않습니다. 템플릿은 건물 및 네트워크 이름을 표시하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-206"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="3be35-207"><sup>2</sup> 이 설정은 서브넷이 회사 네트워크 내부에 있는지 여부를 반영하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-207"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="3be35-208">다른 용도로 사용량을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-208">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="3be35-209"><sup>3</sup> 이 설정은 네트워크에서 Azure ExpressRoute를 사용하는지 여부를 반영하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-209"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="3be35-210">다른 용도로 사용량을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-210">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="3be35-211">**샘플 행:**</span><span class="sxs-lookup"><span data-stu-id="3be35-211">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="3be35-212">네트워크 범위는 슈퍼넷을 나타내는 데 사용할 수 있습니다(단일 라우팅 연결 연결과 여러 서브넷의 조합).</span><span class="sxs-lookup"><span data-stu-id="3be35-212">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="3be35-213">모든 새 건물 업로드는 겹치는 범위에 대해 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-213">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="3be35-214">이전에 건물 파일을 업로드한 경우 현재 파일을 다운로드하고 다시 업로드하여 중복을 식별하고 문제를 해결한 후 다시 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-214">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="3be35-215">이전에 업로드된 파일의 겹치는 경우 보고서의 건물에 서브넷이 잘못 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-215">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="3be35-216">특정 VPN 구현은 서브넷 정보를 정확하게 보고하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-216">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="3be35-217">VPN 열은 선택 사항이며 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-217">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="3be35-218">VPN 열 값이 1로 설정되어 있는 경우 해당 행으로 나타내는 서브넷이 서브넷 내의 모든 IP 주소와 일치하게 완전히 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-218">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span> <span data-ttu-id="3be35-219">이러한 서브넷을 완전히 확장하면 데이터 작성과 관련된 쿼리에 대한 쿼리 타임에 부정적인 영향을 미치기 때문에 VPN 서브넷에만 이 기능을 꼭 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3be35-219">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span> <span data-ttu-id="3be35-220">서브넷의 확장으로 확장 행 제한이 1,000,000,000을 초과하면 건물 파일이 수락되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-220">If the expansion of the subnet results in the expansion row limit of 1,000,000 being exceeded, the building file will not be accepted.</span></span>


### <a name="supernetting"></a><span data-ttu-id="3be35-221">슈퍼네팅</span><span class="sxs-lookup"><span data-stu-id="3be35-221">Supernetting</span></span>

<span data-ttu-id="3be35-222">각 서브넷을 정의하는 대신 일반적으로 Classless Inter-Domain 라우팅(CIDR)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-222">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="3be35-223">*슈퍼넷은* 단일 라우팅 결합을 공유하는 여러 서브넷의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-223">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="3be35-224">각 서브넷에 대한 항목을 추가하는 대신 슈퍼넷 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-224">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="3be35-225">Supernetting은 지원되지만 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-225">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="3be35-226">예를 들어 Contoso의 마케팅 건물은 아래 서브넷으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-226">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="3be35-227">10.1.0.0/24-1층</span><span class="sxs-lookup"><span data-stu-id="3be35-227">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="3be35-228">10.1.1.0/24-2층</span><span class="sxs-lookup"><span data-stu-id="3be35-228">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="3be35-229">10.1.2.0/24-3층</span><span class="sxs-lookup"><span data-stu-id="3be35-229">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="3be35-230">10.1.3.0/24-4층</span><span class="sxs-lookup"><span data-stu-id="3be35-230">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="3be35-231">각 서브넷에 대한 항목을 추가하는 대신 이 예제에서는 슈퍼넷 주소를 사용할 수 있습니다(예: 10.1.0.0/22).</span><span class="sxs-lookup"><span data-stu-id="3be35-231">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="3be35-232">네트워크 = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="3be35-232">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="3be35-233">네트워크 범위 = 22</span><span class="sxs-lookup"><span data-stu-id="3be35-233">Network Range = 22</span></span>

<span data-ttu-id="3be35-234">슈퍼네팅을 구현하기 전에 고려해야 할 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-234">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="3be35-235">Supernetting은 8비트에서 28비트 마스크로 서브넷 매핑에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-235">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="3be35-236">수퍼네팅을 진행하는 데는 시간이 덜 걸리지만 데이터의 풍부성을 줄이는 비용이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-236">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="3be35-237">서브넷 10.1.2.0과 관련된 품질 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-237">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="3be35-238">슈퍼넷을 구현한 경우 서브넷이 있는 위치 또는 서브넷이 있는 네트워크 유형(예: 랩)을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-238">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="3be35-239">건물 및 업로드된 바닥 위치 정보를 위해 모든 서브넷을 정의한 경우 해당 구분을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-239">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="3be35-240">슈퍼넷 주소가 올바른지 확인하여 원치 않는 서브넷을 포획하지 않는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-240">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="3be35-241">데이터에서 192.168.0.0을 찾는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-241">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="3be35-242">많은 조직의 경우 사용자가 집에 있는 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-242">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="3be35-243">다른 경우 위성 사무실의 IP 주소 체계입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-243">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="3be35-244">조직에 이 구성을 사용하는 사무실이 있는 경우 일반적인 서브넷을 사용하여 홈 네트워크와 내부 네트워크를 구분하기 어렵기 때문에 건물 파일에 포함하지 [않습니다.](quality-of-experience-review-guide.md#common-subnets)</span><span class="sxs-lookup"><span data-stu-id="3be35-244">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3be35-245">네트워크 범위를 사용하여 슈퍼넷을 나타내는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-245">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="3be35-246">모든 새 건물 데이터 파일 업로드는 겹치는 범위에 대해 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-246">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="3be35-247">이전에 건물 파일을 업로드한 경우 현재 파일을 다운로드하고 다시 업로드하여 중복을 식별하고 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-247">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="3be35-248">이전에 업로드된 파일의 겹치는 경우 보고서의 건물에 서브넷이 잘못 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-248">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="3be35-249">VPN</span><span class="sxs-lookup"><span data-stu-id="3be35-249">VPN</span></span>

<span data-ttu-id="3be35-250">클라이언트가 CQD 데이터를 원본으로 하는 Microsoft 365 Office 365 QoE(환경 품질)에는 VPN 플래그가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-250">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="3be35-251">CQD는 이를 첫 번째 VPN 및 두 번째 VPN 차원으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-251">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="3be35-252">그러나 이 플래그는 등록된 VPN 네트워크 어댑터가 원격 액세스 Windows VPN 공급 업체의 보고에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-252">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="3be35-253">모든 VPN 공급업체가 원격 액세스 어댑터를 올바르게 등록하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-253">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="3be35-254">이 때문에 기본 제공 VPN 쿼리 필터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-254">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="3be35-255">위에서 설명한 VPN 열을 사용하여 VPN 서브넷을 정확하게 표시하고 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-255">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="3be35-256">또한 보고서에서 쉽게 식별할 수 있도록 VPN 네트워크에 레이블을 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-256">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="3be35-257">다음은 VPN 서브넷에 레이블을 지정하는 방법의 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-257">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="3be35-258">VPN **서브넷에** 대해 이 필드에 "VPN"을 입력하여 네트워크 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-258">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![네트워크 이름을 사용하여 VPN을 보여주는 QCD 보고서 스크린샷](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="3be35-260">VPN **서브넷에** 대해 이 필드에 "VPN"을 입력하여 건물 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-260">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![건물 이름을 사용하여 VPN을 보여주는 QCD 보고서 스크린샷](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="3be35-262">VPN 연결은 네트워크 연결 형식이 무선인 경우 유선으로 잘못 분류하는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-262">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="3be35-263">VPN 연결을 통해 품질을 볼 때 연결 유형이 정확하게 식별되었다고 가정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-263">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="3be35-264">엔드포인트 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="3be35-264">Endpoint data file</span></span>

<span data-ttu-id="3be35-265">다른 유형의 CQD 테넌트 데이터 파일은 **엔드포인트** 데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-265">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="3be35-266">열 값은 호출 레코드의 첫 번째 클라이언트 엔드포인트 이름 또는 두 번째 클라이언트 엔드포인트 이름 열에서 엔드포인트 만들기, 모델 또는 입력 정보를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-266">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="3be35-267">업로드하는 데이터 파일의 형식은 업로드하기 전에 유효성 검사 검사를 통과하기 위해 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-267">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="3be35-268">파일은 .tsv 파일(열은 TAB으로 구분) 또는 .csv 파일(열은 콤마로 구분)되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-268">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="3be35-269">데이터 파일의 내용은 테이블 헤더를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-269">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="3be35-270">데이터 파일의 첫 번째 줄은 "EndpointName"처럼 헤더 레이블이 아닌 실제 데이터로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-270">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="3be35-271">모든 7개 열은 문자열 데이터 형식만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-271">All seven columns use the String data type only.</span></span> <span data-ttu-id="3be35-272">허용되는 최대 길이는 64자입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-272">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="3be35-273">데이터 필드는 비어 있을 수 있지만 탭 또는 콤마로 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-273">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="3be35-274">빈 데이터 필드는 빈 문자열 값을 할당하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-274">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="3be35-275">EndpointName은 고유해야 합니다. 그렇지 않으면 업로드가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-275">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="3be35-276">동일한 EndpointName을 사용하는 중복 행 또는 두 개의 행이 있는 경우 충돌로 인해 잘못된 조인이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-276">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="3be35-277">EndpointLabel1, EndpointLabel2 및 EndpointLabel3은 사용자 지정 가능한 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-277">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="3be35-278">"IT 부서 지정 2018 노트북" 또는 "자산 태그 5678"처럼 문자열 또는 값이 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-278">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="3be35-279">각 행에 대해 7개의 열이 있어야 합니다. 열은 다음 순서로 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-279">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="3be35-280">**필드 순서:**</span><span class="sxs-lookup"><span data-stu-id="3be35-280">**Field order:**</span></span>

  <span data-ttu-id="3be35-281">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="3be35-281">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="3be35-282">**샘플 행:**</span><span class="sxs-lookup"><span data-stu-id="3be35-282">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a><span data-ttu-id="3be35-283">건물 파일 업데이트</span><span class="sxs-lookup"><span data-stu-id="3be35-283">Update a building file</span></span>

<span data-ttu-id="3be35-284">건물 및 서브넷 정보를 수집하는 동안 관리자는 시간이 지날수록 건물 파일을 여러 번 업로드하여 새 서브넷과 해당 건물 정보를 사용할 수 있도록 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-284">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="3be35-285">이 경우 건물 파일을 다시 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-285">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="3be35-286">이 프로세스는 다음 섹션에 설명된 몇 가지 예외를 제외하고 이전 섹션에서 설명한 초기 업로드와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-286">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="3be35-287">한 번씩 하나의 건물 파일만 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-287">Only one building file can be active at a time.</span></span> <span data-ttu-id="3be35-288">여러 건물 파일은 누적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-288">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="3be35-289">새 서브넷 추가</span><span class="sxs-lookup"><span data-stu-id="3be35-289">Add net new subnets</span></span>

<span data-ttu-id="3be35-290">네트워크 토폴로지의 원래 일부가 아니던 CQD에 새 서브넷을 추가해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-290">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="3be35-291">Net 새 서브넷을 추가하기 위해 CQD의 **테넌트** 데이터 업로드 페이지에서 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-291">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="3be35-292">최신 복사본이 없는 경우 원본 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-292">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="3be35-293">CQD에서 현재 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-293">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="3be35-294">원본 건물 파일을 편집하고 새 서브넷을 획득하기 적어도 1일 전에 발생하는 종료 날짜를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-294">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="3be35-295">원래 건물 파일에 새 서브넷을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-295">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="3be35-296">업로드 새로 수정된 건물 파일을 저장하고 이전 건물 파일이 종료된 후 하루 동안 시작 날짜를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-296">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="3be35-297">누락된 서브넷 추가</span><span class="sxs-lookup"><span data-stu-id="3be35-297">Add missing subnets</span></span>

<span data-ttu-id="3be35-298">관리되는 네트워크에 대한 건물 정보를 업로드한 후 관리되는 모든 네트워크는 건물 연결에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-298">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="3be35-299">그러나 항상 그렇지는 않습니다. 일반적으로 몇 가지 서브넷이 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-299">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="3be35-300">이러한 누락된 네트워크를 찾으면  CQD의 환경 품질 보고서에 대한 누락된 서브넷 **보고서를** 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-300">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="3be35-301">그러면 건물 데이터 파일에 정의되지 않은 10개 이상의 오디오 스트림이 있는 모든 서브넷이 표시되고 외부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-301">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="3be35-302">이 목록에 관리되는 네트워크가 없는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3be35-302">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="3be35-303">서브넷이 누락된 경우 다음 절차를 사용하여 원래 건물 데이터 파일을 업데이트하고 CQD에 다시 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-303">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="3be35-304">CQD의 **테넌트 데이터** 업로드 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-304">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="3be35-305">최신 복사본이 없는 경우 원본 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-305">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="3be35-306">CQD에서 현재 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-306">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="3be35-307">새 서브넷을 원래 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-307">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="3be35-308">업로드 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-308">Upload the building file.</span></span> <span data-ttu-id="3be35-309">시작 날짜를 최소 8개월 전에 설정하여 CQD가 기록 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-309">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="3be35-310">조직의 테넌트 데이터만 보기 위해 보고서를 필터링하려면 이 보고서에 두 번째 테넌트 ID에 대한 쿼리 필터로 테넌트 **ID를** 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-310">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="3be35-311">그렇지 않으면 보고서에 페더리된 서브넷이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-311">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="3be35-312">월별 보고서 필터를 현재 월로 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-312">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="3be35-313">편집 **을** 선택하고  월별 보고서 필터를 조정하여 새 기본 월을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3be35-313">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3be35-314">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3be35-314">Related topics</span></span>

[<span data-ttu-id="3be35-315">CQD에 대한 건물 맵 만들기</span><span class="sxs-lookup"><span data-stu-id="3be35-315">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="3be35-316">통화 품질 향상 및 모니터링 Teams</span><span class="sxs-lookup"><span data-stu-id="3be35-316">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="3be35-317">CQD란?</span><span class="sxs-lookup"><span data-stu-id="3be35-317">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="3be35-318">CQD(통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="3be35-318">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="3be35-319">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="3be35-319">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="3be35-320">CQD를 사용하여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="3be35-320">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="3be35-321">CQD에서 사용할 수 있는 차원 및 측정값</span><span class="sxs-lookup"><span data-stu-id="3be35-321">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="3be35-322">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="3be35-322">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="3be35-323">CQD Power BI 분석하는 데 Power BI 사용</span><span class="sxs-lookup"><span data-stu-id="3be35-323">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
