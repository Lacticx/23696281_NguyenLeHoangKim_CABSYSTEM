# Ma trận các bên liên quan (Stakeholder Matrix) - Dự án CAB System

Dưới đây là biểu đồ phân tích các bên liên quan dựa trên mức độ **Quyền lực (Power)** và **Sự quan tâm (Interest)** đối với dự án hệ thống đặt xe CAB System.

## 1. Biểu đồ Ma trận Power - Interest

```mermaid
quadrantChart
    title Ma trận Stakeholder - CAB System
    x-axis "Ít quan tâm" --> "Rất quan tâm"
    y-axis "Quyền lực thấp" --> "Quyền lực cao"
    quadrant-1 "Manage Closely"
    quadrant-2 "Keep Satisfied"
    quadrant-3 "Monitor"
    quadrant-4 "Keep Informed"
    
    %% Tọa độ [x, y] với dải giá trị từ 0.0 đến 1.0
    "Ban Lãnh đạo ABC": [0.85, 0.9]
    "Đối tác Thanh toán": [0.3, 0.8]
    "Đối tác Bản đồ (API)": [0.25, 0.75]
    "Khách hàng": [0.8, 0.35]
    "Tài xế": [0.85, 0.4]
    "Nhân viên Vận hành": [0.75, 0.3]
    "Đội ngũ Dự án (PM, BA, Dev)": [0.9, 0.45]
    "Nhà cung cấp SMS/Email": [0.2, 0.6]
