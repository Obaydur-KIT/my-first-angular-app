classDiagram
direction BT
class payroll {
   bigint boma
   int county
   datetime2 created
   bigint created_by
   int payam
   int state
   int status
   int sync_status
   datetime2 updated
   bigint updated_by
   int version
   int locked_status
   bigint id
}
class payroll_alternate {
   int age
   varchar(100) first_name
   int gender
   varchar(100) last_name
   varchar(100) middle_name
   varchar(100) nick_name
   varchar(50) phone_number
   bigint payroll_biometric_id
   bigint payroll_data_id
   varchar(50) national_id
   bigint id
}
class payroll_biometric {
   varchar(max) left_index
   varchar(max) left_middle
   varchar(max) left_ring
   varchar(max) left_small
   varchar(max) left_thumb
   varchar(max) photo
   varchar(max) right_index
   varchar(max) right_middle
   varchar(max) right_ring
   varchar(max) right_small
   varchar(max) right_thumb
   bigint id
}
class payroll_data {
   varchar(20) create_date
   varchar(100) enrollment_no
   float exchange_rate
   int ben_id
   int wage_payment_req_id
   int wage_req_ben_trans_id
   int work_id
   varchar(50) payment_cycle
   varchar(20) req_from_date
   varchar(100) req_no
   varchar(20) req_to_date
   varchar(30) status
   int to_attendance
   float wage_rate_ssp_total
   float wage_rate_usd
   float wage_rate_usd_total
   varchar(50) work_code
   bigint payroll_household_id
   bigint payroll_id
   int support_type
   bigint id
}
class payroll_house_hold {
   int age
   varchar(100) first_name
   int gender
   varchar(100) last_name
   varchar(100) middle_name
   varchar(100) nick_name
   varchar(50) phone_number
   bigint payroll_biometric_id
   varchar(100) house_hold_number
   bigint id
}
class payroll_recon {
   varchar(20) amount
   varchar(50) attendance
   varchar(30) created_at
   varchar(30) date_form
   varchar(30) date_to
   varchar(100) enrolment_number
   varchar(20) exchange_rate
   varchar(100) first_name
   varchar(30) generated_at
   varchar(100) household_number
   varchar(100) last_name
   varchar(50) latitude
   varchar(50) longitude
   varchar(50) paid_to
   varchar(20) status
   varchar(100) supervisor_id
   varchar(100) sur_name
   varchar(100) trans_id
   varchar(30) updated_at
   varchar(100) uuid
   varchar(20) wage
   varchar(100) work_code
   varchar(100) work_id
   varchar(200) payment_center
   int payment_count
   bigint id
}

payroll_alternate  -->  payroll_biometric : payroll_biometric_id:id
payroll_alternate  -->  payroll_data : payroll_data_id:id
payroll_data  -->  payroll : payroll_id:id
payroll_data  -->  payroll_house_hold : payroll_household_id:id
payroll_house_hold  -->  payroll_biometric : payroll_biometric_id:id
