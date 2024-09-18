// cypress/integration/formAutomation.spec.js

describe('Form Automation Test', () => {
  it('Fills the questionnaire form automatically', () => {
    // Visit the form URL
    cy.visit('https://docs.google.com/forms/d/e/1FAIpQLSd8kxrEBU0sgJujV7eYAO6exg_DX8MBOtrR-SkRBOhtM72Rjw/viewform?usp=sf_link')

    // Fill in the 'Nama Aplikasi

    cy.get('input[type="text"]').first().type('Nama Aplikasi Contoh') // Mengisi field nama aplikasi
    
    // Select the 'Jenis Pengguna Aplikasi'
    cy.get('div[role="listbox"]').eq(0).click()
    cy.contains('Individu').click() // Pilih opsi Individu atau Perusahaan

    // Mengisi 'Jumlah Pengguna Aplikasi'
    cy.get('input[type="number"]').type('100')

    // Mengisi 'Kapan Aplikasi didirikan' (tanggal)
    cy.get('input[type="date"]').type('2022-05-01')

    // Submit the form (asumsikan tombol submit ada di akhir form)
    cy.contains('Submit').click()
  })
})
